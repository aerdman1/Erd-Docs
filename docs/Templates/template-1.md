---
title: Templates
deprecated: false
hidden: false
metadata:
  robots: index
---
## Owlbert API and SDK Documentation

<Image align="right" width="100px" src="https://files.readme.io/e0a6918a86cf324138d1d4cea87a8005638575eca8c68a26c284a682e52cbfc9-Nametag.psd.full.png" />

Explore the tools and resources you need to streamline your integration process— \<br>whether using pre-built solutions or full API access.

<HTMLBlock>{`
<a  href="https://docs.example.com" class="btn-primary">
  <i class="fas fa-rocket"></i> Get Started
</a>
`}</HTMLBlock>

## Integration Approaches

<Cards columns={3}>
  <Card title="No-Code" icon="fa-mouse-pointer">
    Implement our hosted solution with minimal setup—no coding required.
  </Card>

  <Card title="Low-Code" icon="fa-tools">
    Utilize our SDKs and pre-configured components for quick integration.
  </Card>

  <Card title="Full-Code" icon="fa-code">
    Gain complete control with API endpoints, webhooks, and custom workflows.
  </Card>
</Cards>

## Key Features

<Cards columns={3}>
  <Card title="Document Processing" icon="fa-file-alt">
    Extract and verify data from IDs, passports, and official documents.
  </Card>

  <Card title="Biometric Authentication" icon="fa-user-check">
    Securely validate users through facial recognition and liveness detection.
  </Card>

  <Card title="Access Control" icon="fa-lock">
    Implement OAuth-based authentication and robust security policies.
  </Card>
</Cards>

## Developer Resources

<Columns layout="auto">
  <Column>
    **Mobile SDKs**\
    Ready-to-use SDKs for iOS and Android to accelerate mobile integration.
  </Column>

  <Column>
    **API Documentation**\
    Detailed API specs, response formats, and integration best practices.
  </Column>
</Columns>

<HTMLBlock>{`
<style>
/* Hide Table of Contents */
.content-toc {
  display: none;
}
  
  /* Hide Header */
  .rm-Guides #content-head {
  display:none;
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
    font-size:2.5em;
}

.content-body p {
    color: var(--gray-600);
    font-size: 1rem;
    line-height: 1.5;
}

/* Primary Button */
.content-body .btn-primary {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background-color: var(--red);
    color: white;
    font-size: 18px;
    padding: 12px 24px;
    border-radius: 8px;
    font-weight: 500;
    text-decoration: none !important;
    transition: background-color 0.3s;
    border: none;
    cursor: pointer;
}

.content-body .btn-primary:hover {
    background-color: #FE0022;
    opacity: 0.95;
}

/* Font Awesome Icon inside Button */
.content-body .btn-primary i {
    font-size: 18px;
    vertical-align: middle;
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