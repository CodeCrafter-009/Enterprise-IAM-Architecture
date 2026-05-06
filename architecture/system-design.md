# Identity Architecture Flow

The following diagram outlines the flow of identity from the on-premise Active Directory through Okta to the downstream Service Providers.
```mermaid
graph TD
    subgraph "Source of Truth"
        AD[Active Directory Windows Server 2019]
    end
    
    subgraph "Identity Provider (IdP)"
        Okta[Okta IAM Platform]
    end
    
    subgraph "Service Providers (SPs)"
        SF[Salesforce - Live SAML]
        GL[GitLab - Mock RBAC]
        SN[ServiceNow - Mock RBAC]
    end

    AD --"Okta AD Agent (Syncs Users & Groups)"--> Okta
    Okta --"SAML 2.0 Assertion (SSO)"--> SF
    Okta --"Group Rules Auto-Provisioning"--> GL
    Okta --"Group Rules Auto-Provisioning"--> SN
