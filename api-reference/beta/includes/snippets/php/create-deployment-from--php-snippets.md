---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;
use Microsoft\Graph\Generated\Models\Deployment;
use Microsoft\Graph\Generated\Models\CatalogContent;
use Microsoft\Graph\Generated\Models\FeatureUpdateCatalogEntry;
use Microsoft\Graph\Generated\Models\DeploymentSettings;
use Microsoft\Graph\Generated\Models\ScheduleSettings;
use Microsoft\Graph\Generated\Models\RateDrivenRolloutSettings;
use Microsoft\Graph\Generated\Models\MonitoringSettings;
use Microsoft\Graph\Generated\Models\MonitoringRule;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Deployment();
$requestBody->setOdataType('#microsoft.graph.windowsUpdates.deployment');
$content = new CatalogContent();
$content->setOdataType('#microsoft.graph.windowsUpdates.catalogContent');
$contentCatalogEntry = new FeatureUpdateCatalogEntry();
$contentCatalogEntry->setOdataType('#microsoft.graph.windowsUpdates.featureUpdateCatalogEntry');
$contentCatalogEntry->setId('f341705b-0b15-4ce3-aaf2-6a1681d78606');
$content->setCatalogEntry($contentCatalogEntry);
$requestBody->setContent($content);
$settings = new DeploymentSettings();
$settings->setOdataType('microsoft.graph.windowsUpdates.deploymentSettings');
$settingsSchedule = new ScheduleSettings();
$settingsScheduleGradualRollout = new RateDrivenRolloutSettings();
$settingsScheduleGradualRollout->setOdataType('#microsoft.graph.windowsUpdates.rateDrivenRolloutSettings');
$settingsScheduleGradualRollout->setDurationBetweenOffers(new \DateInterval('P7D'));
$additionalData = [
	'devicePerOffer' => 100,
];
$settingsScheduleGradualRollout->setAdditionalData($additionalData);
$settingsSchedule->setGradualRollout($settingsScheduleGradualRollout);
$settings->setSchedule($settingsSchedule);
$settingsMonitoring = new MonitoringSettings();
$monitoringRulesMonitoringRule1 = new MonitoringRule();
$monitoringRulesMonitoringRule1->setSignal(new MonitoringSignal('rollback'));
$monitoringRulesMonitoringRule1->setThreshold(5);
$monitoringRulesMonitoringRule1->setAction(new MonitoringAction('pauseDeployment'));
$monitoringRulesArray []= $monitoringRulesMonitoringRule1;
$settingsMonitoring->setMonitoringRules($monitoringRulesArray);

$settings->setMonitoring($settingsMonitoring);
$requestBody->setSettings($settings);

$result = $graphServiceClient->admin()->windows()->updates()->deployments()->post($requestBody)->wait();

```