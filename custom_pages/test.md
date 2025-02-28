---
title: Test
fullscreen: false
hidden: false
---
// PullExamples.jsx - Upload this to ReadMe Custom Components

import React from 'react';

export default function PullExamples({ path, method }) {
  if (typeof oas === 'undefined') {
    return (
      <div style={{ padding: '1em', backgroundColor: '#ffecec', border: '1px solid #f5aca6', borderRadius: '5px' }}>
        ⚠️ <strong>PullExamples</strong> can only be used on custom pages where the OpenAPI specification (`oas`) is available.
      </div>
    );
  }

  const operation = oas.operation(path, method);

  if (!operation) {
    return (
      <div style={{ padding: '1em', backgroundColor: '#ffecec', border: '1px solid #f5aca6', borderRadius: '5px' }}>
        ⚠️ No operation found for <strong>{method.toUpperCase()} {path}</strong>.
      </div>
    );
  }

  const requestExample = operation?.requestBody?.content?.['application/json']?.example;

  const responses = Object.entries(operation.responses || {}).map(([statusCode, response]) => {
    const responseExample = response?.content?.['application/json']?.example;
    return {
      statusCode,
      description: response.description,
      responseExample,
    };
  });

  return (
    <div style={{
      border: '1px solid #ddd',
      padding: '16px',
      borderRadius: '8px',
      backgroundColor: '#f9f9f9',
      marginBottom: '16px',
      fontFamily: 'Arial, sans-serif'
    }}>
      <h3 style={{ margin: '0 0 12px 0', fontWeight: 'bold' }}>
        {operation.summary || `${method.toUpperCase()} ${path}`}
      </h3>
      <p><strong>Method:</strong> {method.toUpperCase()}</p>
      <p><strong>Path:</strong> {path}</p>

      <h4 style={{ margin: '16px 0 8px 0' }}>Request Example</h4>
      {requestExample ? (
        <pre style={{
          backgroundColor: '#f0f0f0',
          padding: '12px',
          borderRadius: '4px',
          overflowX: 'auto'
        }}>
          {JSON.stringify(requestExample, null, 2)}
        </pre>
      ) : (
        <p>No request body example available.</p>
      )}

      <h4 style={{ margin: '16px 0 8px 0' }}>Response Examples</h4>
      {responses.length > 0 ? (
        responses.map(({ statusCode, description, responseExample }) => (
          <div key={statusCode} style={{ marginBottom: '12px' }}>
            <p><strong>Status {statusCode}</strong>: {description}</p>
            {responseExample ? (
              <pre style={{
                backgroundColor: '#f0f0f0',
                padding: '12px',
                borderRadius: '4px',
                overflowX: 'auto'
              }}>
                {JSON.stringify(responseExample, null, 2)}
              </pre>
            ) : (
              <p>No example available for status {statusCode}.</p>
            )}
          </div>
        ))
      ) : (
        <p>No response examples available.</p>
      )}
    </div>
  );
}

## Update a Pet

To update a pet, use the following request and response examples.

<PullExamples />