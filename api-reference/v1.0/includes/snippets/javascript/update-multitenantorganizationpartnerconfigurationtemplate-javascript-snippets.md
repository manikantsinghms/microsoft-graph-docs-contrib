---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const multiTenantOrganizationPartnerConfigurationTemplate = {
    inboundTrust: {
        isMfaAccepted: true,
        isCompliantDeviceAccepted: true,
        isHybridAzureADJoinedDeviceAccepted: true
    },
    automaticUserConsentSettings: {
        inboundAllowed: true,
        outboundAllowed: true
    },
    templateApplicationLevel: 'newPartners,existingPartners'
};

await client.api('/policies/crossTenantAccessPolicy/templates/multiTenantOrganizationPartnerConfiguration')
	.update(multiTenantOrganizationPartnerConfigurationTemplate);

```