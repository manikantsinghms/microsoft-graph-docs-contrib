---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php
use Microsoft\Graph\GraphServiceClient;


$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);


$graphServiceClient->administrativeUnits()->byAdministrativeUnitId('administrativeUnit-id')->scopedRoleMembers()->byScopedRoleMembershipId('scopedRoleMembership-id')->delete()->wait();

```