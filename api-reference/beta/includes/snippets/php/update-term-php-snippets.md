---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;
use Microsoft\Graph\Generated\Models\Term;
use Microsoft\Graph\Generated\Models\LocalizedLabel;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Term();
$labelsLocalizedLabel1 = new LocalizedLabel();
$labelsLocalizedLabel1->setName('changedLabel');
$labelsLocalizedLabel1->setLanguageTag('en-US');
$labelsLocalizedLabel1->setIsDefault(true);
$labelsArray []= $labelsLocalizedLabel1;
$requestBody->setLabels($labelsArray);


$result = $graphServiceClient->termStore()->sets()->bySetId('set-id')->terms()->byTermId('term-id')->patch($requestBody)->wait();

```