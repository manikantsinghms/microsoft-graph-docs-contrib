---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



departments, err := graphClient.Security().Labels().Departments().ByDepartmentTemplateId("departmentTemplate-id").Get(context.Background(), nil)


```