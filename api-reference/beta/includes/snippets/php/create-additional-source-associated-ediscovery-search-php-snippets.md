---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;
use Microsoft\Graph\Generated\Models\SiteSource;
use Microsoft\Graph\Generated\Models\Site;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SiteSource();
$requestBody->setOdataType('microsoft.graph.security.siteSource');
$site = new Site();
$site->setWebUrl('https://m365x809305.sharepoint.com/sites/Design-topsecret');
$requestBody->setSite($site);

$result = $graphServiceClient->security()->cases()->ediscoveryCases()->byEdiscoveryCaseId('ediscoveryCase-id')->searches()->byEdiscoverySearchId('ediscoverySearch-id')->additionalSources()->post($requestBody)->wait();

```