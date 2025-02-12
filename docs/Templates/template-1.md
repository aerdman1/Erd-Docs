---
title: Template 1
deprecated: false
hidden: false
metadata:
  robots: index
---
# Getting Started

Welcome to our documentation! Choose the best way to integrate our API.

[GET STARTED](https://docs.example.com)

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
    --red: #EE2C46;
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

/* Buttons */
a {
    display: inline-block;
    background-color: var(--red);
    color: white;
    font-size: 18px;
    padding: 12px 24px;
    border-radius: 8px;
    font-weight: 500;
    text-decoration: none;
    transition: background-color 0.3s;
}

a:hover {
    background-color: #FE0022;
    color: white;
}

/* Cards */
.CardsGrid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-top: 20px;
}

.Card {
    background: white;
    border-radius: 8px;
    padding: 24px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
    text-align: center;
}

.Card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.Card:hover .Card-icon {
    animation: spin 0.4s ease-in-out;
}

.Card-title {
    font-size: 1.25rem;
    margin: 12px 0;
    font-weight: bold;
}

/* Spinning Icons */
@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(720deg); } /* Two full spins */
}

.Card-icon {
    font-size: 24px;
    color: var(--red);
}

/* Columns */
.Columns {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-top: 30px;
}

.Column {
    background: var(--gray-100);
    padding: 20px;
    border-radius: 8px;
}

/* Responsive Design */
@media (max-width: 1024px) {
    .CardsGrid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 768px) {
    .CardsGrid {
        grid-template-columns: 1fr;
    }
    
    .Columns {
        grid-template-columns: 1fr;
    }
}
</style>
`}</HTMLBlock>

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