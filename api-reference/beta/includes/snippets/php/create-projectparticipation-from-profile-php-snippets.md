---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;
use Microsoft\Graph\Generated\Models\ProjectParticipation;
use Microsoft\Graph\Generated\Models\CompanyDetail;
use Microsoft\Graph\Generated\Models\PositionDetail;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ProjectParticipation();
$requestBody->setCategories(['Branding', 	]);
$client = new CompanyDetail();
$client->setDisplayName('Contoso Ltd.');
$client->setDepartment('Corporate Marketing');
$client->setWebUrl('https://www.contoso.com');
$requestBody->setClient($client);
$requestBody->setDisplayName('Contoso Re-branding Project');
$detail = new PositionDetail();
$detailCompany = new CompanyDetail();
$detailCompany->setDisplayName('Adventureworks Inc.');
$detailCompany->setDepartment('Consulting');
$detailCompany->setWebUrl('https://adventureworks.com');
$detail->setCompany($detailCompany);
$detail->setDescription('Rebranding of Contoso Ltd.');
$detail->setJobTitle('Lead PM Rebranding');
$detail->setRole('project management');
$detail->setSummary('A 6 month project to help Contoso rebrand after they were divested from a parent organization.');
$requestBody->setDetail($detail);

$result = $graphServiceClient->me()->profile()->projects()->post($requestBody)->wait();

```