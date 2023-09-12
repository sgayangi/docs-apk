# API Policies - Overview

API policies are a powerful tool in WSO2 APK for enforcing business logic and modifying API requests and responses. You can attach policies at the gateway-level, API-level or operation-level, in either the request or response flow. WSO2 APK comes with a set of default policies that cover most common use cases that will suit your specific needs.

## Policy Attachment Levels

There are a few levels where a Policy attachment can happen in APK resources. 

| **Level**              | **Actor**      | **Description**  |
|------------------------|----------------|------------------|
| Gateway                | System Admin   | Any policy which is applicable to all the APIs deployed to gateway runtime should be attached to `Gateway` resource. |     
| API                    | API Owner      |  Attach a policy which is applicable to all the operations of that API.  |   
| Operation               | API Owner      |  Attach a policy to an operation of a API.   |

Attaching a policy to a specific level is descibed under each policy.


## Policy Execution Order

When you have multiple policies attached in different levels policies, you need to aware about in which order they are excuted in runtime. The following table describes the execution order. Top one executed at first and the bottom one exected at last.

<table>
<tbody>
  <tr>
    <td>Authentication Policy</td>
  </tr>
  <tr>
    <td>Global level Interceptor Service Policy</td>
  </tr>
  <tr>
    <td>API / Operation level Interceptor Service Policy</td>
  </tr>
  <tr>
    <td>Static Header Manipulation Policy</td>
  </tr>
</tbody>
</table>

## Create API Policies via REST API or via CRs

Keep in mind that you cannot attach an API policy at two separate levels simultaneously and that the approach for attaching policies varies depending on the interface that you are using (i.e., CLI or REST API interface) to create the APIs.

| **Create an API from:** | **Attach Policies**                                             |
|-------------------------|-----------------------------------------------------------------|
| REST APIs               | Attach a policy at API-level or Operation-level                 |
| Custom Resources (CRs)  | Attach a policy at Gateway-level, API-level or Operation-level  |  

When you attach a policy at the API-level, it will be applied globally to all the operations that correspond to the API. However, when you attach a policy at an operation level, it will only be applicable locally to a specific operation.

## What's Next?

- [Learn to attach API Policies for Interceptor Services](../interceptors/interceptors-overview/)
- [Learn to attach API Policies for Backend JWT Token Manipulation](../backend-jwt-token-manipulation/backend-jwt-token-manipulation-via-rest-api/)
- [Learn to attach API Policies for CORS](../cors/enable-cors-via-rest-api/)
  
