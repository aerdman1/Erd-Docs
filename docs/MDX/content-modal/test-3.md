---
title: test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
## Introducción

En BancoEstado, reafirmamos nuestro compromiso con la innovación y la mejora continua de nuestros servicios digitales. A través de nuestras APIs, ponemos a disposición de tu empresa un conjunto sólido de herramientas diseñadas para impulsar su transformación digital, optimizar procesos y facilitar la integración tecnológica de forma ágil, segura y eficiente.

### Objetivo

Este documento tiene como objetivo entregar toda la información necesaria para una implementación exitosa del flujo completo de pago TEF en Open Finance BancoEstado: desde la generación del consentimiento hasta la ejecución del pago. En particular, se describen las APIs clave, detallando sus funcionalidades, requisitos técnicos y consideraciones operativas para asegurar su correcta utilización.

### Descripción General

El servicio de **Iniciación de pagos TEF Persona Natural (PN)** es un servicio "On-Line" que permite la ejecución de transferencias electrónicas de fondos vía APIs. Este servicio facilita la integración entre el sistema del cliente (ERP) y el sistema de transferencias del banco, asegurando que toda la comunicación entre Cliente/Banco y Banco/Cliente se realice bajo encriptación y con altos estándares de seguridad.

Para habilitar esta comunicación, BancoEstado dispone de una plataforma que, mediante un proceso de enrolamiento seguro, otorga acceso para el intercambio de información desde y hacia el banco vía API. La integración involucra mTLS (intercambio de certificados de seguridad), los cuales deben ser obtenidos desde el portal API Market. Más adelante, el flujo contempla la correcta obtención y configuración de certificados mTLS.

### Finalidad

| Finalidad | Descripción                                                                                     | APIs habilitadas      |
| --------- | ----------------------------------------------------------------------------------------------- | --------------------- |
| PAGO      | Iniciación de una transferencia electrónica de fondos (TEF) autorizada por el usuario del banco | TEF PN (/pn/payments) |

### URL de consumo de APIs

| Referencia              | Ambiente             | URL                                                                                                                                                                                                                                                          |
| ----------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| KEYCLOAK_HOST_AND_REALM | Sandbox              | [https://iam-api.open-banking-mtls-prod.bancoestado.cl/realms/consent-management-prd/protocol/openid-connect/token](https://iam-api.open-banking-mtls-prod.bancoestado.cl/realms/consent-management-prd/protocol/openid-connect/token)                       |
| KEYCLOAK_HOST_AND_REALM | Producción           | [https://iam-api.open-banking-mtls-prod.bancoestado.cl/realms/consent-management-production-prd/protocol/openid-connect/token](https://iam-api.open-banking-mtls-prod.bancoestado.cl/realms/consent-management-production-prd/protocol/openid-connect/token) |
| API_HOST                | Sandbox / Producción | [https://openfinance.open-banking-mtls-prod.bancoestado.cl](https://openfinance.open-banking-mtls-prod.bancoestado.cl)                                                                                                                                       |

### Autenticación

Bearer Token (Authorization: Bearer \<access_token>) + mTLS (--cert / --key requeridos en todas las llamadas).

Las credenciales de acceso (certificados mTLS y client_id) son proporcionadas por BancoEstado durante el proceso de onboarding en API Market.

### Scope para finalidad PAGO

| Scope          | Descripción                                                                           | APIs que habilita |
| -------------- | ------------------------------------------------------------------------------------- | ----------------- |
| CreatePayments | Iniciación de una transferencia electrónica de fondos (TEF) autorizada por el usuario | POST /pn/payments |

### Resumen del flujo completo

A continuación, se muestra el resumen del flujo completo de Iniciación de Pagos TEF con todos los pasos que se deben realizar tanto de la Empresa como BancoEstado.

| # | Paso                                          | Responsable     | Etapa      |
| - | --------------------------------------------- | --------------- | ---------- |
| 1 | Obtener Token (client_credentials)            | Empresa         | Generación |
| 2 | Iniciar Consentimiento (initConsent + JAR)    | Empresa         | Generación |
| 3 | Redirigir usuario al banco (authorizationUrl) | Empresa → Banco | Generación |
| 4 | Intercambiar código por access token (PKCE)   | Empresa         | Generación |
| 5 | Inspección del token → obtener consentId      | Empresa         | Generación |
| 6 | Ejecutar pago TEF — Persona Natural (PN)      | Empresa         | Consumo    |

## Generación del Consentimiento

Los siguientes pasos describen el flujo completo de generación del consentimiento requerido para la iniciación de un pago TEF (finalidad PAGO).

Al completar el Paso 5 se obtiene el consentId, credencial que habilita la ejecución del pago en la Sección 3 de Consumo del Consentimiento — Ejecución del Pago TEF.

### Paso 1 — Obtener Token (client_credentials)

Esta llamada a la API se utiliza para obtener un token de acceso de corta duración (300 segundos) que se utilizará en solicitudes posteriores. Obtener un Bearer Token de la Empresa mediante el flujo OAuth2 client_credentials desde el servidor IAM.

**Estructura de la llamada**

| Campo        | Valor                                                            |
| ------------ | ---------------------------------------------------------------- |
| Método       | POST                                                             |
| URL          | KEYCLOAK_HOST_AND_REALM (ver tabla de b. URL de consumo de APIs) |
| Content-Type | application/x-www-form-urlencoded                                |

**Parámetros (form-urlencoded)**

| Campo      | Tipo            | Requerido | Descripción                                                      |
| ---------- | --------------- | --------- | ---------------------------------------------------------------- |
| grant_type | Cadena de texto | Sí        | Valor fijo: client_credentials                                   |
| scope      | Cadena de texto | Sí        | Valor fijo: openid                                               |
| client_id  | Cadena de texto | Sí        | Identificador único de la Empresa, proporcionado por BancoEstado |

**Ejemplo cURL**

```bash
curl --location '${KEYCLOAK_HOST_AND_REALM}' \
  --cert /path/to/certificate.crt --key /path/to/private-key.key \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'grant_type=client_credentials' \
  --data-urlencode 'scope=openid' \
  --data-urlencode 'client_id=${CLIENT_ID}'
```

**Respuesta del servicio**

| Código           | Descripción                          | Campos clave                         |
| ---------------- | ------------------------------------ | ------------------------------------ |
| 200 OK           | Token generado correctamente         | access_token, expires_in, token_type |
| 400 Bad Request  | Parámetros inválidos o faltantes     | error, error_description             |
| 401 Unauthorized | client_id o credenciales incorrectas | error, error_description             |

**Ejemplo respuesta**

```json
{
  "access_token": "<ACCESS_TOKEN>",
  "expires_in": 300,
  "refresh_expires_in": 0,
  "token_type": "Bearer",
  "id_token": "<ID_TOKEN>",
  "not-before-policy": 0,
  "scope": "openid profile receptor"
}
```

**Definición de campos de respuesta**

| Campo              | Descripción                                                                                                                                                                                      |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| access_token       | Token de acceso emitido por el servidor de autorización.                                                                                                                                         |
| expires_in         | Tiempo de vida del access_token en segundos.                                                                                                                                                     |
| refresh_expires_in | Tiempo de vida del refresh_token en segundos. El valor 0 indica que el token de actualización no expira o que no fue emitido.                                                                    |
| token_type         | Tipo de token emitido.                                                                                                                                                                           |
| id_token           | Token de identidad definido por el protocolo OpenID Connect (OIDC). Contiene información sobre la autenticación del usuario en formato JWT.                                                      |
| not-before-policy  | Indica la fecha/hora (en Unix timestamp) a partir de la cual el token es válido. El valor 0 significa que el token es válido inmediatamente desde su emisión.                                    |
| scope              | Define los permisos concedidos al token. En este caso: openid (autenticación OIDC), profile (acceso a datos básicos del perfil del usuario) y receptor (permiso personalizado de la aplicación). |

### Paso 2 — Iniciar Consentimiento (initConsent)

La Empresa construye un JAR (JWT Authorization Request) firmado con sus credenciales y lo envía al servidor de consentimiento.

El JAR contiene la finalidad (scope), los datos del pago y los recursos solicitados. El cuerpo de la solicitud de esta API debe ser firmado con la llave privada registrada en el Portal API Market (estándar JAR FAPI 2.0).

**Estructura de la llamada**

| Campo        | Valor                                                      |
| ------------ | ---------------------------------------------------------- |
| Método       | POST                                                       |
| URL          | ${API_HOST}/consent-management/api/v1/consents/initConsent |
| Content-Type | application/json                                           |

**Definición de campos de llamada**

| Campo     | Tipo            | Requerido | Descripción                                                       |
| --------- | --------------- | --------- | ----------------------------------------------------------------- |
| client_id | Cadena de texto | Sí        | Identificador del cliente Empresa                                 |
| request   | Cadena de texto | Sí        | JWT firmado (JAR) con scope, datos del pago y parámetros FAPI 2.0 |

### Cuerpo JAR FAPI 2.0 — Ejemplo completo (payload)

```json
{
  "iss": "${CLIENT_ID}",
  "sub": "${CLIENT_ID}",
  "issuer": "${API_HOST}",
  "aud": "${API_HOST}/oidc",
  "response_type": "code",
  "client_id": "${CLIENT_ID}",
  "redirect_uri": "${REDIRECT_URI}",
  "scope": "openid CreatePayments",
  "state": "${STATE}",
  "nonce": "${NONCE}",
  "code_challenge": "${CODE_CHALLENGE}",
  "code_challenge_method": "S256",
  "authorization_details": [
  {
  	"type": "PAYMENT_INITIATION",
  	"data": {
    	"rut": "${RUT_CLIENTE}",
    	"personType": "${PERSON_TYPE}"
  	},
  	"actions": [
    	"INITIATE",
    	"STATUS",
    	"CANCEL"
  	],
  	"payment": {
    	"type": "TEF",
    	"instructedAmount": {
      	  "date": "${FECHA_PAGO}",
      	  "currency": "CLP",
      	  "amount": "${MONTO}"
    	},
    	"purpose": "${GLOSA_PAGO}",
    	"details": {
      	  "creditor": {
        	    "personType": "PN",
        	    "document": "${RUT_DESTINATARIO}",
        	    "name": "${NOMBRE_DESTINATARIO}"
      	  },
      	"creditorAccount": {
        	  "number": "${NRO_CUENTA}",
        	  "issuer": "${CODIGO_SBIF}",
        	  "fantasyName": "${NOMBRE_BANCO}",
        	  "accountType": "${TIPO_CUENTA}"
      	}
        }
  	  }
  }
  ],
  "jti": "${UUID_UNICO}",
  "iat": "${TIMESTAMP_ACTUAL}",
  "exp": "${TIMESTAMP_ACTUAL_MAS_300}",
  "nbf": "${TIMESTAMP_ACTUAL}"
}
```

**Ejemplo cURL**

```bash
curl --location \
 --request POST '${API_HOST}/consent-management/api/v1/consents/initConsent' \
  --cert /path/to/certificate.crt --key /path/to/private-key.key \
  --header 'Authorization: Bearer ${ACCESS_TOKEN}' \
  --header 'Content-Type: application/json' \
  --data '{"client_id": "${CLIENT_ID}", "request": "${JAR}"}'
```

**Respuesta del servicio**

| Código           | Descripción                           | Campos clave             |
| ---------------- | ------------------------------------- | ------------------------ |
| 201 Created      | Consentimiento iniciado correctamente | authorizationUrl         |
| 400 Bad Request  | JAR inválido o parámetros faltantes   | error, error_description |
| 401 Unauthorized | Token inválido o expirado             | error, error_description |

**Ejemplo respuesta**

```json
{
  "authorizationUrl": "<AUTHORIZATION_URL>"
}
```

### Paso 3 — Redirigir usuario al banco (authorizationUrl)

La Empresa redirige al usuario al valor de authorizationUrl retornado en el Paso 2.

El banco presenta la pantalla de autorización del pago al usuario.

<Callout icon="🚧" theme="warn">
  ### Este paso es gestionado íntegramente por el banco. La Empresa solo redirige y espera el retorno.
</Callout>

| Estado del banco | Resultado                                                                      |
| ---------------- | ------------------------------------------------------------------------------ |
| Aprobado         | El banco redirige a redirect_uri con parámetro: code=\<código de autorización> |
| Rechazado        | El banco redirige a redirect_uri con parámetro: error=access_denied            |

**Estructura de la llamada**

```bash
curl --location '${authorizationUrl}'
```

**Definición de campos de llamada**

| Campo  | Valor            |
| ------ | ---------------- |
| Método | GET              |
| URL    | authorizationUrl |

Este HTML contiene la URL de la aplicación BECH donde será redirigido el cliente desde la Empresa, para que este último autorice el consentimiento de pago (En este punto el cliente verá información del consentimiento creado, podrá elegir la cuenta y finalmente autorizar el consentimiento mediante los medios de autenticación de BECH).

Al finalizar el proceso de autorización en la aplicación BECH, el cliente será redirigido de vuelta a la Empresa por la redirect url configurada en portal:

**Ejemplo de respuesta**

```
HTML 303: Redirecting to https://<URL_BECH>/login?uid=<UID>&cookies=<COOKIES_SESSION>
```

### Paso 4 — Intercambiar código por access token (PKCE)

Con el código de autorización recibido del banco, la Empresa solicita el access token del usuario enviando el code_verifier PKCE generado al construir el JAR.

**Estructura de la llamada**

| Campo        | Valor                             |
| ------------ | --------------------------------- |
| Método       | POST                              |
| URL          | ${API_HOST}/oidc/token            |
| Content-Type | application/x-www-form-urlencoded |

| Campo         | Tipo            | Requerido | Descripción                                            |
| ------------- | --------------- | --------- | ------------------------------------------------------ |
| grant_type    | Cadena de texto | Sí        | Valor fijo: authorization_code                         |
| code          | Cadena de texto | Sí        | Código de autorización recibido en la redirect_uri     |
| redirect_uri  | Cadena de texto | Sí        | URI de retorno registrada para la Empresa              |
| client_id     | Cadena de texto | Sí        | Identificador del cliente Empresa                      |
| code_verifier | Cadena de texto | Sí        | Verificador PKCE generado al construir el JAR (Paso 2) |

**Ejemplo cURL**

```bash
curl --location --request POST '${API_HOST}/oidc/token' \
  --cert /path/to/certificate.crt --key /path/to/private-key.key \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'grant_type=authorization_code' \
  --data-urlencode 'code=${AUTH_CODE}' \
  --data-urlencode 'redirect_uri=${REDIRECT_URI}' \
  --data-urlencode 'client_id=${CLIENT_ID}' \
  --data-urlencode 'code_verifier=${CODE_VERIFIER}'
```

**Respuesta del servicio (200)**

```json
{
  "access_token": "<ACCESS_TOKEN>",
  "expires_in": 3600,
  "id_token": "<ID_TOKEN>",
  "refresh_token": "<REFRESH_TOKEN>",
  "scope": "openid CreatePayments",
  "token_type": "Bearer"
}
```

**Definición de campos de respuesta**

| Campo         | Descripción                                                                                                                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| access_token  | Token de acceso emitido por el servidor de autorización.                                                                                                                                         |
| expires_in    | Tiempo de vida del access_token en segundos.                                                                                                                                                     |
| id_token      | Token de identidad definido por el protocolo OpenID Connect (OIDC). Contiene información sobre la autenticación del usuario en formato JWT.                                                      |
| refresh_token | Token de acceso emitido por el servidor de autorización para renovación del token.                                                                                                               |
| scope         | Define los permisos concedidos al token. En este caso: openid (autenticación OIDC), profile (acceso a datos básicos del perfil del usuario) y receptor (permiso personalizado de la aplicación). |
| token_type    | Tipo de token emitido.                                                                                                                                                                           |

### Paso 4.b — Obtener un nuevo token (solo si expirado)

Para hacer un refresh y obtener un nuevo token, este paso se debe realizar solo si ha expirado el token anterior.

**Estructura de la llamada**

| Campo        | Valor                             |
| ------------ | --------------------------------- |
| Método       | POST                              |
| URL          | ${API_HOST}/oidc/token            |
| Content-Type | application/x-www-form-urlencoded |

| Campo         | Tipo            | Requerido | Descripción                                            |
| ------------- | --------------- | --------- | ------------------------------------------------------ |
| grant_type    | Cadena de texto | Sí        | Valor fijo: authorization_code                         |
| code          | Cadena de texto | Sí        | Código de autorización recibido en la redirect_uri     |
| redirect_uri  | Cadena de texto | Sí        | URI de retorno registrada para la Empresa              |
| client_id     | Cadena de texto | Sí        | Identificador del cliente Empresa                      |
| code_verifier | Cadena de texto | Sí        | Verificador PKCE generado al construir el JAR (Paso 2) |

**Ejemplo cURL**

```bash
curl --location '${API_HOST}/oidc/token' \
--cert /path/to/certificate.crt --key /path/to/private-key.key \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=refresh_token' \
--data-urlencode 'client_id=<CLIENT_ID>' \
--data-urlencode 'refresh_token=<REFRESH_TOKEN>'
```

**Respuesta del servicio (200)**

```json
{
  "access_token": "<ACCESS_TOKEN>",
  "expires_in": 3600,
  "id_token": "<ID_TOKEN>",
  "refresh_token": "<REFRESH_TOKEN>",
  "scope": "openid CreatePayments",
  "token_type": "Bearer"
}
```

**Definición de campos de respuesta**

| Campo         | Descripción                                                                                                                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| access_token  | Token de acceso emitido por el servidor de autorización.                                                                                                                                         |
| expires_in    | Tiempo de vida del access_token en segundos.                                                                                                                                                     |
| id_token      | Token de identidad definido por el protocolo OpenID Connect (OIDC). Contiene información sobre la autenticación del usuario en formato JWT.                                                      |
| refresh_token | Token de acceso emitido por el servidor de autorización para renovación del token.                                                                                                               |
| scope         | Define los permisos concedidos al token. En este caso: openid (autenticación OIDC), profile (acceso a datos básicos del perfil del usuario) y receptor (permiso personalizado de la aplicación). |
| token_type    | Tipo de token emitido.                                                                                                                                                                           |

### Paso 5 — Inspección del token — obtener consentId

La Empresa inspecciona el access token del usuario para obtener el consentId. Este consentId es el identificador del consentimiento de pago autorizado y se usa como credencial para ejecutar el pago en la Sección 3 de Consumo del Consentimiento — Ejecución del Pago TEF.

**Estructura de la llamada**

| Campo        | Valor                                |
| ------------ | ------------------------------------ |
| Método       | POST                                 |
| URL          | ${API_HOST}/oidc/token/introspection |
| Content-Type | application/x-www-form-urlencoded    |

| Campo     | Tipo            | Requerido | Descripción                                    |
| --------- | --------------- | --------- | ---------------------------------------------- |
| token     | Cadena de texto | Sí        | Access token del usuario obtenido en el Paso 4 |
| client_id | Cadena de texto | Sí        | Identificador del cliente Empresa              |

**Ejemplo cURL**

```bash
curl --location --request POST '${API_HOST}/oidc/token/introspection' \
  --cert /path/to/certificate.crt --key /path/to/private-key.key \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'token=${USER_ACCESS_TOKEN}' \
  --data-urlencode 'client_id=${CLIENT_ID}'
```

**Respuesta del servicio (200)**

```json
{
  "active": true,
  "sub": "<SUBJECT_ID>",
  "consentId": "<CONSENT_ID>",
  "client_id": "<CLIENT_ID>",
  "exp": 1781754204,
  "iat": 1781750604,
  "iss": "<ISSUER_URL>",
  "aud": "<AUDIENCE_URL>",
  "scope": "openid CreatePayments",
  "token_type": "Bearer"
}
```

**Definición de campos de respuesta**

| Campo      | Descripción                                                                                                                                                 |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| active     | Indica si el token está activo y vigente. El valor true significa que el token es válido y puede ser utilizado para acceder a los recursos protegidos.      |
| sub        | (Subject) Identificador único del usuario o entidad a quien fue emitido el token. Es un claim estándar de JWT que representa al titular del token.          |
| consentId  | Identificador único del consentimiento otorgado por el usuario. Relaciona el token con un registro específico de autorización/consentimiento en el sistema. |
| client_id  | Identificador de la aplicación cliente que solicitó el token al servidor de autorización.                                                                   |
| exp        | (Expiration Time) Fecha y hora de expiración del token en formato Unix timestamp. Después de este momento, el token no debe ser aceptado.                   |
| iat        | (Issued At) Fecha y hora en que el token fue emitido, en formato Unix timestamp. Permite calcular el tiempo de vida transcurrido del token.                 |
| iss        | (Issuer) URL del servidor de autorización que emitió el token. El receptor debe validar que este valor corresponde al emisor esperado.                      |
| aud        | (Audience) URL o identificador del destinatario para el cual el token fue emitido. El servidor de recursos debe verificar que está incluido en este campo.  |
| scope      | Permisos concedidos al token. En este caso: openid (autenticación OIDC) y CreatePayments (permiso para iniciar o crear pagos).                              |
| token_type | Tipo de token emitido. El valor Bearer indica que el portador del token puede usarlo directamente para acceder a los recursos protegidos.                   |

<Callout icon="🚧" theme="warn">
  ### El campo consentId obtenido en este paso es la credencial de pago. Se usa como valor del campo "token" en los Pasos 6. Guardar este valor antes de continuar.
</Callout>

## Consumo del Consentimiento — Ejecución del Pago TEF

Una vez completada la generación del consentimiento (Sección 2) y obtenido el consentId (Paso 5), la Empresa puede ejecutar la transferencia TEF. El consentId se envía como valor del campo "token" en el body del endpoint de pago.

| Tipo de pago | Endpoint                                                | Titular         |
| ------------ | ------------------------------------------------------- | --------------- |
| Pago PN      | POST ${API_HOST}/api/v1/srvrecnormativo-api/pn/payments | Persona Natural |

### Paso 6 — Ejecutar Pago Persona Natural (PN)

Con el consentId obtenido en el Paso 5, la Empresa ejecuta la transferencia TEF para una cuenta de Persona Natural.

**Estructura de la llamada**

| Campo        | Valor                                              |
| ------------ | -------------------------------------------------- |
| Método       | POST                                               |
| URL          | ${API_HOST}/api/v1/srvrecnormativo-api/pn/payments |
| Content-Type | application/json                                   |

**Definición de campos de llamada**

| Campo | Tipo            | Requerido | Descripción                                                                            |
| ----- | --------------- | --------- | -------------------------------------------------------------------------------------- |
| token | Cadena de texto | Sí        | consentId obtenido en la inspección del Paso 5. Es la credencial que autoriza el pago. |

**Ejemplo cURL**

```bash
curl --location --request POST '${API_HOST}/api/v1/srvrecnormativo-api/pn/payments' \
  --cert /path/to/certificate.crt --key /path/to/private-key.key \
  --header 'Authorization: Bearer ${ACCESS_TOKEN}' \
  --header 'Content-Type: application/json' \
  --data '{"token": "${CONSENT_ID}"}'
```

**Respuesta del servicio**

| Código           | Descripción                      | Campos clave                                       |
| ---------------- | -------------------------------- | -------------------------------------------------- |
| 200 OK           | Pago iniciado correctamente      | "transactionID": ID de la transacción TEF generada |
| 400 Bad Request  | Token inválido o pago rechazado  | "mensaje": descripción del error                   |
| 401 Unauthorized | Access token inválido o expirado | Renovar token y reintentar                         |

**Respuesta exitosa (200)**

```json
{
  "codigo": 200,
  "mensaje": "OK",
  "resultado": "E",
  "payload": {
    	"amount": "1001",
    	"accountingDate": "2026-06-12T00:00:00.000Z",
    	"transactionID": "<TRANSACTION_ID>",
    	"beneficiaryAccount": "<ACCOUNT_NUMBER>"
  },
  "codigoOperacion": "0000"
}
```

<Callout icon="🚧" theme="warn">
  ### El campo transactionID identifica la transacción TEF iniciada. Para consultar el estado del pago, gestionar reintentos o manejar errores, utilice la Guía de Gestión de Pagos TEF de Open Finance BancoEstado.
</Callout>

## Flujo de Rechazo del Consentimiento

Cuando el usuario decide no autorizar el pago en el banco (Paso 3 “Redirigir usuario al banco (authorizationUrl)”), el banco redirige al usuario de vuelta a la redirect_uri de la Empresa con un parámetro de error. No se genera consentId y no es posible ejecutar el pago. Para reintentar, debe iniciar el flujo desde el Paso 1.

```
HTML 303: Redirecting to <REDIRECT_URL>?error=access_denied&error_description=User+cancelled+the+interaction&state=<STATE>&iss=<ISSUER_URL>&cookies=<COOKIES_SESSION>
```

### Retorno con rechazo del banco

| Parámetro         | Valor              | Descripción                                                 |
| ----------------- | ------------------ | ----------------------------------------------------------- |
| error             | access_denied      | El usuario rechazó el consentimiento de pago                |
| error_description | User denied access | Descripción del motivo de rechazo                           |
| state             | ${STATE}           | Valor state enviado en el JAR para correlación de la sesión |

### Comparación de flujos

| Paso              | Flujo Aprobado             | Flujo Rechazado                          |
| ----------------- | -------------------------- | ---------------------------------------- |
| 1 — Token         | Token obtenido             | Token obtenido                           |
| 2 — initConsent   | authorizationUrl retornada | authorizationUrl retornada               |
| 3 — Banco         | Usuario aprueba el pago    | Usuario rechaza — error en redirect_uri  |
| 4 — Intercambio   | access_token obtenido      | No aplica                                |
| 5 — Inspección    | consentId obtenido         | No aplica                                |
| 6 — Ejecutar pago | transactionID retornado    | Flujo terminado. Reiniciar desde Paso 1. |

## Anexo

### Códigos de Respuestas – API Iniciación de Pagos TEF PN

En este anexo se presentan los códigos de respuesta que pueden retornar la API de Iniciación de Pagos TEF durante la ejecución de las operaciones. Para cada código se indica el código de respuesta, el estado HTTP asociado y la descripción correspondiente.

| Code         | Status Code | Descripción                                                                   |
| ------------ | ----------- | ----------------------------------------------------------------------------- |
| SRN.PAY.0000 | 200         | Operación exitosa                                                             |
| SRN.PAY.0002 | 400         | Parámetros de entrada incorrectos                                             |
| SRN.PAY.1010 | 400         | Error al validar cuenta perfilada                                             |
| SRN.PAY.1011 | 400         | Error al validar destinatario                                                 |
| SRN.PAY.1012 | 400         | Error al crear destinatario                                                   |
| SRN.PAY.1021 | 400         | Monto máximo excedido                                                         |
| SRN.PAY.1022 | 400         | Cantidad máxima excedida                                                      |
| SRN.PAY.1030 | 400         | Parámetros de primera transferencia inválidos                                 |
| SRN.PAY.1050 | 400         | Rut denegado                                                                  |
| SRN.PAY.1060 | 400         | Error en pre-autorización                                                     |
| SRN.PAY.1070 | 500         | Error al ejecutar transferencia                                               |
| SRN.PAY.2001 | 403         | El rutCompany es requerido para validar el perfilamiento                      |
| SRN.PAY.2002 | 400         | No se definió la cabecera: x-fapi-interaction-id                              |
| SRN.PAY.2003 | 403         | La empresa no cuenta con el scope necesario para esta acción                  |
| SRN.PAY.2004 | 403         | El concentimiento no tiene un estado autorizado                               |
| SRN.PAY.2005 | 403         | La empresa no cuenta con el perfilamiento necesario para esta acción          |
| SRN.PAY.2006 | 500         | Error al obtener el consentimiento                                            |
| SRN.PAY.2007 | 500         | Error al obtener el perfilamiento                                             |
| SRN.PAY.2008 | 500         | Error al obtener el bank token                                                |
| SRN.PAY.3001 | 403         | La empresa o el usuario no se encuentran activos para realizar esta operación |
| SRN.PAY.3002 | 500         | Error al obtener el perfilamiento                                             |
| SRN.PAY.3008 | 400         | Cuenta inexistente para el rut                                                |
