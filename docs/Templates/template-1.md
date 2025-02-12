---
title: Getting Started - Template 1
deprecated: false
hidden: false
metadata:
  robots: index
---

# Getting Started

Welcome to our documentation! Choose the best way to integrate our API.

<a class="btn-primary" href="https://docs.example.com">GET STARTED</a>

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
    **Mobile SDKs**  
    Native SDKs for iOS and Android platforms.
  </Column>

  <Column>
    **API Reference**  
    Complete API documentation with examples and best practices.
  </Column>
</Columns>

<HTMLBlock>{`
<style>
/* Hide Table of Contents */
.content-toc {
  display: none;
}

/* Ensure content-body width */
.rm-Guides .content-body {
    max-width: 100%;
    width: 100%;
}

/* Remove border under header */
.rm-Guides #content-head {
    border-bottom: 1px solid var(--color-border-default);
    padding-bottom: 30px;
}

/* Scope styles only inside .content-body */
.content-body {
    --primary-blue: #0066FF;
    --primary-hover: #0052CC;
    --gray-50: #F9FAFB;
    --gray-100: #F3F4F6;
    --gray-600: #4B5563;
    --red: #EE2C46;
}

/* Typography */
.content-body h1, 
.content-body h2 {
    color: #111827;
    font-weight: bold;
    margin-bottom: 16px;
}

.content-body p {
    color: var(--gray-600);
    font-size: 1rem;
    line-height: 1.5;
}

/* Primary Button */
.content-body .btn-primary {
    display: inline-block;
    background-color: var(--red);
    color: white;
    font-size: 18px;
    padding: 12px 24px;
    border-radius: 8px;
    font-weight: 500;
    text-decoration: none;
    transition: background-color 0.3s;
    border: none;
    cursor: pointer;
}

.content-body .btn-primary:hover {
    background-color: #FE0022;
    opacity: 0.95;
}

/* Cards */
.content-body .CardsGrid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-top: 20px;
}

.content-body .Card {
    background: white;
    border-radius: 8px;
    padding: 24px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
    text-align: center;
}

.content-body .Card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.content-body .Card:hover .Card-icon {
    animation: spin 0.4s ease-in-out;
}

.content-body .Card-title {
    font-size: 1.25rem;
    margin: 12px 0;
    font-weight: bold;
}

/* Spinning Icons */
@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(720deg); } /* Two full spins */
}

.content-body .Card-icon {
    font-size: 24px;
    color: var(--red);
}

/* Columns */
.content-body .Columns {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-top: 30px;
}

.content-body .Column {
    background: var(--gray-100);
    padding: 20px;
    border-radius: 8px;
}

/* Responsive Design */
@media (max-width: 1024px) {
    .content-body .CardsGrid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 768px) {
    .content-body .CardsGrid {
        grid-template-columns: 1fr;
    }
    
    .content-body .Columns {
        grid-template-columns: 1fr;
    }
}
</style>
`}</HTMLBlock>
