---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



subcategories, err := graphClient.Security().Labels().Categories().ByCategoryTemplateId("categoryTemplate-id").Subcategories().Get(context.Background(), nil)


```