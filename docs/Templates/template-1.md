---
title: Template 1
deprecated: false
hidden: false
metadata:
  robots: index
---
# Getting Started

<Accordion title="Introduction" icon="fa-info-circle">
  Welcome to our documentation! Choose the best way to integrate our API.
</Accordion>

## Integration Options

<Cards columns={3}>
  <Card title="No Code" icon="fa-mouse-pointer">
    Quick integration through our hosted web interface.
  </Card>

  <Card title="Low Code" icon="fa-tools">
    Simplified SDK integration with pre-built components.
  </Card>

  <Card title="Full Code" icon="fa-code">
    Complete API control for full customization.
  </Card>
</Cards>

## API Capabilities

<Cards columns={3}>
  <Card title="Documents" icon="fa-file-alt">
    Validate passports, driver's licenses, and identity documents.
  </Card>

  <Card title="Face Identification" icon="fa-user-check">
    Authenticate users using facial recognition and liveness detection.
  </Card>

  <Card title="OAuth" icon="fa-lock">
    Secure authentication and authorization for API access.
  </Card>
</Cards>

## Development Tools

<Columns layout="auto">
  <Column>
    **Mobile SDKs**\
    Native SDKs for iOS and Android platforms.
  </Column>

  <Column>
    **API Reference**\
    Complete API documentation with examples and best practices.
  </Column>
</Columns>

<HTMLBlock>{`
<style>
:root {
    --primary-blue: #0066FF;
    --primary-hover: #0052CC;
    --gray-50: #F9FAFB;
    --gray-100: #F3F4F6;
    --gray-600: #4B5563;
}

/* Typography */
h1, h2 {
    color: #111827;
    font-weight: bold;
    margin-bottom: 16px;
}

p {
    color: var(--gray-600);
    font-size: 1rem;
    line-height: 1.5;
}

/* Accordion */
.accordion {
    background: white;
    padding: 16px;
    border-radius: 8px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

/* Cards */
.card {
    background: white;
    border-radius: 8px;
    padding: 16px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
}

.card:hover {
    transform: translateY(-4px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

/* Tabs */
.tabs {
    margin-top: 24px;
}

.tabs .tab {
    font-weight: bold;
    padding: 12px 20px;
    border-bottom: 2px solid transparent;
    transition: color 0.2s ease, border-color 0.2s ease;
}

.tabs .tab.active {
    color: var(--primary-blue);
    border-bottom: 2px solid var(--primary-blue);
}

.tabs .tab:hover {
    color: var(--primary-hover);
}
  
</style>
`}</HTMLBlock>