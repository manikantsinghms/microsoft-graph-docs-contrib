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



authenticationEventListeners, err := graphClient.Identity().AuthenticationEventListeners().ByAuthenticationEventListenerId("authenticationEventListener-id").Get(context.Background(), nil)


```