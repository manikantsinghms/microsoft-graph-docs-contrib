---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;
use Microsoft\Graph\Generated\Models\MacOSOfficeSuiteApp;
use Microsoft\Graph\Generated\Models\MimeContent;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new MacOSOfficeSuiteApp();
$requestBody->setOdataType('#microsoft.graph.macOSOfficeSuiteApp');
$requestBody->setDisplayName('Display Name value');
$requestBody->setDescription('Description value');
$requestBody->setPublisher('Publisher value');
$largeIcon = new MimeContent();
$largeIcon->setOdataType('microsoft.graph.mimeContent');
$largeIcon->setType('Type value');
$largeIcon->setValue(\GuzzleHttp\Psr7\Utils::streamFor(base64_decode('dmFsdWU=')));
$requestBody->setLargeIcon($largeIcon);
$requestBody->setIsFeatured(true);
$requestBody->setPrivacyInformationUrl('https://example.com/privacyInformationUrl/');
$requestBody->setInformationUrl('https://example.com/informationUrl/');
$requestBody->setOwner('Owner value');
$requestBody->setDeveloper('Developer value');
$requestBody->setNotes('Notes value');
$requestBody->setPublishingState(new MobileAppPublishingState('processing'));

$result = $graphServiceClient->deviceAppManagement()->mobileApps()->post($requestBody)->wait();

```