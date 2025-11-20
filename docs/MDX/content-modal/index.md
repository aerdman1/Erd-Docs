---
title: Content Modal
excerpt: Content Modal
deprecated: false
hidden: false
icon: far fa-arrows-maximize
link:
  new_tab: false
metadata:
  robots: index
---
<br />

<ContentModal
  label="Open Example Modal"
  title="Example Modal"
  modalId="exampleModal"
  buttonColor="#2B6CB0"
  buttonPadding="12px 18px"
  size="sm"
  content={
    <HTMLBlock>{`
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
    Fusce vel leo ut turpis feugiat commodo et in nunc. Phasellus imperdiet ut nunc vitae porta. 
    Pellentesque sollicitudin, sapien sed dictum molestie, dolor enim vestibulum est, non facilisis libero nibh vel arcu. 
    Fusce aliquam diam in velit vulputate luctus. Morbi sagittis erat eget est consectetur, a molestie dui sollicitudin. 
    Mauris commodo lorem eros, a cursus tortor malesuada ac. Ut sit amet eros dictum, aliquet nisl rutrum, finibus nulla. 
    Sed interdum commodo interdum. Quisque arcu diam, malesuada sit amet eros non, vulputate aliquet orci.
    `}</HTMLBlock>
  }
/>

{user.MyVariable}

<Accordion title="My Accordion Title" icon="fa-info-circle">
  Lorem ipsum dolor sit amet, **consectetur adipiscing elit.** Ut enim
  ad minim veniam, quis nostrud exercitation ullamco. Excepteur sint
  occaecat cupidatat non proident!
</Accordion>

<br />

```mermaid
sequenceDiagram
    title WEB PUSH PROVISIONING (APPLE PAY)

    participant U as User
    participant CW as "Client Website"
    participant CB as "Client Backend"
    participant A as Apple
    participant S as Scheme
    participant P as PayTech
    participant DF as "Digitisation Flow"

    U->>CW: Load page
    U->>CW: Press 'Add to Apple Pay'

    CW->>CW: Execute Apple JS
    CW->>CW: Call jwsResolverCallback ()

    CW->>CB: Retrieve Token  Object

    Note over CB,A: - Generate\nSharingInstanceIdentifier\n- Create JWS\n- Encapsulate JWS to Token\nObject

    CB->>A: Send Token Object to Apple Pay Web App
    A->>A: Display Pop Up\nWindow

    A-->>U: Sign In to Apple Account

    CB->>A: getProvisioningTarget
    A->>P: GET search -device -tokens
    P-->>CB: getProvisioningTarget   (response)

    CB->>A: Show list of eligible devices
    A-->>U: Select device & agree to T&C's

    CB->>P: getProvisioningCredential
    P->>CB: POST provisioning  -data -request
    P-->>CB: getProvisioningCredential   (response)

    CB->>DF: Digitize Card (Green flow)
    DF-->>CB: Digitisation Flow

```
