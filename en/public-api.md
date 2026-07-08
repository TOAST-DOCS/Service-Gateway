<!-- pre-align:aligned sig=0f36aac40dbd -->

<a id="network-service-gateway-api-v2-guide"></a>

## Network > Service Gateway > API v2 Guide

NHN Cloud Network services use IaaS tokens for authentication and authorization when making API calls. The IaaS token is an authentication token used for NHN Cloud's OpenStack-based infrastructure services (IaaS). For more information on issuing and using IaaS tokens, please refer to the [IaaS Token](/nhncloud/en/public-api/iaas-token).

For Service Gateway APIs, the `network` type endpoint is used. For more details, see `serviceCatalog` from the response of token issuance.

| Type | Region | Endpoint |
|---|---|---|
| network | Korea (Pangyo) Region<br>Korea (Pyeongchon) Region<br>Korea (Gwangju) Region | https://kr1-api-network-infrastructure.nhncloudservice.com<br>https://kr2-api-network-infrastructure.nhncloudservice.com<br>https://kr3-api-network-infrastructure.nhncloudservice.com |

In each API response, you may find fields that are not specified within this guide. Those fields are for NHN Cloud internal usage, so refrain from using them because they may be changed without prior notice.

<a id="service-gateway"></a>

## Service Gateway

<a id="get-a-list-of-service-gateways"></a>

### Get a List of Service Gateways

```
GET /v2.0/gateways/servicegateways
X-Auth-Token: {tokenId}
```

<a id="request"></a>

#### Request
This API does not require a request body.

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| id | Query | UUID | - | The ID of the service gateway to retrieve |
| name | Query | String | - | The name of the service gateway to retrieve |
| service_endpoint_id | Query | UUID | - | The service endpoint ID of the service gateway to retrieve |
| network_id | Query | UUID | - | The VPC ID of the service gateway to retrieve |
| subnet_id | Query | UUID | - | The subnet ID of the service gateway to retrieve |
| port_id | Query | UUID | - | The port ID of the service gateway to retrieve |
| fixed_ip| Query | String | - | The IP address of the service gateway to retrieve |
include_gateway_identity| Query | Boolean | - | Whether to use fixed NAT IP address |


<a id="response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| servicegateways | Body | Array | A list of service gateway information objects |
| servicegateways.id | Body | UUID | The ID of the service gateway |
| servicegateways.name | Body | String | The name of the service gateway |
| servicegateways.port_id | Body | UUID | Port ID |
| servicegateways.tenant_id | Body | String | Tenant ID |
| servicegateways.network_id | Body | UUID | VPC ID |
| servicegateways.subnet_id | Body | UUID | Subnet ID |
| servicegateways.fixed_ip | Body | String | The IP address of the service gateway |
| servicegateways.include_gateway_identity| Body | Boolean | Whether to use fixed NAT IP address |
| servicegateways.service_endpoint_id | Body | UUID | Service endpoint ID |
| servicegateways.description | Body | String | The description for the service gateway |

<details><summary>Example</summary>

```json
{
  "servicegateways": [
    {
      "status": "AVAILABLE",
      "include_gateway_identity": true,
      "description": "",
      "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
      "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
      "fixed_ip": "192.168.0.82",
      "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
      "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
      "create_time": "2023-08-31 02:11:09",
      "project_id": "302406c4a1d44b2cb2bc07a652c0b202",
      "port_id": "182a31be-9e29-400d-983b-f701cf9b4bbc",
      "id": "d383a4a3-dae7-4609-b2db-ecdf5859fac5",
      "name": "sgw_test"
    }
  ]
}
```
</details>

---
<a id="get-a-service-gateway"></a>

### Get a Service Gateway

```
GET /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

<a id="get-a-service-gateway-request"></a>

#### Request
This API does not require a request body.

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| serviceGatewayId | URL | UUID | O | The ID of the service gateway |

<a id="get-a-service-gateway-response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| servicegateway | Body | Object | Service gateway information object|
| servicegateway.id | Body | UUID | The ID of the service gateway |
| servicegateway.name | Body | String | The name of the service gateway |
| servicegateway.port_id | Body | UUID | Port ID |
| servicegateway.tenant_id | Body | String | Tenant ID |
| servicegateway.network_id | Body | UUID | VPC ID |
| servicegateway.subnet_id | Body | UUID | Subnet ID |
| servicegateway.fixed_ip | Body | String | The IP address of the service gateway |
| servicegateway.include_gateway_identity| Body | Boolean | Whether to use fixed NAT IP address |
| servicegateway.service_endpoint_id | Body | UUID | Service endpoint ID |
| servicegateway.api_endpoints | Body | Array | List of API endpoint information objects |
| servicegateway.api_endpoints.domain_name | Body | String | API endpoint domain |
| servicegateway.description | Body | String | The description for the service gateway |

<details><summary>Example</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "include_gateway_identity": true,
    "description": "",
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "api_endpoints": [
      {
        "domain_name": "test.test.com"
      }
    ],
    "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
    "create_time": "2023-08-31 02:11:09",
    "project_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "port_id": "182a31be-9e29-400d-983b-f701cf9b4bbc",
    "id": "d383a4a3-dae7-4609-b2db-ecdf5859fac5",
    "name": "sgw_test"
  }
}
```
</details>

---
<a id="create-a-service-gateway"></a>

### Create a Service Gateway

```
POST /v2.0/gateways/servicegateways
X-Auth-Token: {tokenId}
```

<a id="create-a-service-gateway-request"></a>

#### Request

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| servicegateway | Body | Object | O | Service gateway information object |
| servicegateway.name | Body | String | - | The name of the service gateway |
| servicegateway.description | Body | String | - | The description for the service gateway |
| servicegateway.network_id | Body | UUID | O | VPC ID |
| servicegateway.subnet_id | Body | UUID | O | Subnet ID |
| servicegateway.fixed_ip | Body | String | - | Service gateway IP address |
| servicegateway.include_gateway_identity| Body | Boolean | - | Whether to use fixed NAT IP address |
| servicegateway.service_endpoint_id | Body | UUID | O | Service endpoint ID |




<details><summary>Example</summary>

```json
{
  "servicegateway": {
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "fixed_ip": "192.168.0.82",
    "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
    "name": "sgw_test",
    "description": "test"
  }
}
```
</details>

<a id="create-a-service-gateway-response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| servicegateway | Body | Object | A list of service gateway information objects |
| servicegateway.id | Body | UUID | The ID of the service gateway |
| servicegateway.name | Body | String | The name of the service gateway |
| servicegateway.port_id | Body | UUID | Port ID |
| servicegateway.tenant_id | Body | String | Tenant ID |
| servicegateway.network_id | Body | UUID | VPC ID |
| servicegateway.subnet_id | Body | UUID | Subnet ID |
| servicegateway.fixed_ip | Body | String | The IP address of the service gateway |
| servicegateway.include_gateway_identity| Body | Boolean | Whether to sue fixed NAT IP address |
| servicegateway.service_endpoint_id | Body | UUID | Service endpoint ID |
| servicegateway.api_endpoints | Body | Array | List of API endpoint information objects |
| servicegateway.api_endpoints.domain_name | Body | String | API endpoint domain |
| servicegateway.description | Body | String | The description for the service gateway |


<details><summary>Example</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "description": "",
    "include_gateway_identity": false,
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "api_endpoints": [
      {
        "domain_name": "test.test.com"
      }
    ],
    "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
    "create_time": "2023-08-31 02:11:09",
    "project_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "port_id": "182a31be-9e29-400d-983b-f701cf9b4bbc",
    "id": "d383a4a3-dae7-4609-b2db-ecdf5859fac5",
    "name": "sgw_test"
  }
}
```
</details>

---
<a id="modify-a-service-gateway"></a>

### Modify a Service Gateway

```
PUT /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

<a id="modify-a-service-gateway-request"></a>

#### Request

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| serviceGatewayId | URL | UUID | O | The ID of the service gateway |
| servicegateway | Body | Object | O | Service gateway information object |
| servicegateway.name | Body | String | - | The name of the service gateway |
| servicegateway.description | Body | String | - | The description for the service gateway |

<details><summary>Example</summary>

```json
{
  "servicegateway": {
    "name": "sgw_test1",
    "description": "test1"
  }
}
```
</details>

<a id="modify-a-service-gateway-response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| servicegateway | Body | Object | Service gateway information object |
| servicegateway.id | Body | UUID | The ID of the service gateway |
| servicegateway.name | Body | String | The name of the service gateway |
| servicegateway.port_id | Body | UUID | Port ID |
| servicegateway.tenant_id | Body | String | Tenant ID |
| servicegateway.network_id | Body | UUID | VPC ID |
| servicegateway.subnet_id | Body | UUID | Subnet ID |
| servicegateway.fixed_ip | Body | String | The IP address of the service gateway |
| servicegateway.include_gateway_identity| Body | Boolean | Whether to use fixed NAT IP address |
| servicegateway.service_endpoint_id | Body | UUID | Service endpoint ID |
| servicegateway.api_endpoints | Body | Array | List of API endpoint information objects |
| servicegateway.api_endpoints.domain_name | Body | String | API endpoint domain |
| servicegateway.description | Body | String | The description for the service gateway |


<details><summary>Example</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "include_gateway_identity": false,
    "description": "test1",
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "api_endpoints": [
      {
        "domain_name": "test.test.com"
      }
    ],
    "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
    "create_time": "2023-08-31 02:11:09",
    "project_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "port_id": "182a31be-9e29-400d-983b-f701cf9b4bbc",
    "id": "d383a4a3-dae7-4609-b2db-ecdf5859fac5",
    "name": "sgw_test1"
  }
}
```
</details>

---
<a id="delete-a-service-gateway"></a>

### Delete a Service Gateway

```
DELETE /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

<a id="delete-a-service-gateway-request"></a>

#### Request
This API does not require a request body.

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| serviceGatewayId | URL | UUID | O | The ID of the service gateway |


<a id="delete-a-service-gateway-response"></a>

#### Response
Stops the specified node group.










<a id="service-endpoint"></a>

## Service Endpoint

<a id="get-a-list-of-service-endpoints"></a>

### Get a List of Service Endpoints

```
GET /v2.0/gateways/serviceendpoints/
X-Auth-Token: {tokenId}
```

<a id="get-a-list-of-service-endpoints-request"></a>

#### Request
This API does not require a request body.

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| id | Query | UUID | - | The ID of the service endpoint to retrieve |
| display_name | Query | UUID | - | The name of the service endpoint to retrieve |



<a id="get-a-list-of-service-endpoints-response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| serviceendpoints | Body | Array | List of service endpoint information objects |
| serviceendpoints.id | Body | UUID | Service endpoint ID |
| serviceendpoints.display_name | Body | String | The name of the service endpoint to appear in the console |
| serviceendpoints.support_gateway_identity | Body | Boolean | Whether to use fixed NAT IP address |
| serviceendpoints.description | Body | String | The description for the service endpoint |

<details><summary>Example</summary>

```json
{
  "serviceendpoints": [
    {
      "display_name": "Object Storage",
      "support_gateway_identity": true,
      "description": "",
      "name": "OBS",
      "id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5"
    }
  ]
}
```
</details>

---
<a id="get-a-service-endpoint"></a>

### Get a Service Endpoint

```
GET /v2.0/gateways/serviceendpoints/{seerviceEndpointId}
X-Auth-Token: {tokenId}
```

<a id="get-a-service-endpoint-request"></a>

#### Request
This API does not require a request body.

| Name | Type | Format | Required | Description |
|---|---|---|---|---|
| tokenId | Header | String | O | Token ID |
| serviceEndpointId | URL | UUID | O | Service endpoint ID |

<a id="get-a-service-endpoint-response"></a>

#### Response

| Name | Type | Format | Description |
|---|---|---|---|
| serviceendpoint | Body | Object | Service endpoint information object  |
| serviceendpoint.id | Body | UUID | Service endpoint ID |
| serviceendpoint.display_name | Body | String | The name of the service endpoint to appear in the console |
| serviceendpoint.support_gateway_identity | Body | Boolean | Whether to use fixed NAT IP address |
| serviceendpoint.description | Body | String | The description for the service endpoint |

<details><summary>Example</summary>

```json
{
  "serviceendpoint": {
      "display_name": "Object Storage",
      "support_gateway_identity": true,
      "description": "",
      "name": "OBS",
      "id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5"
  }
}
```
</details>

---
<a id="section-1"></a>

## Custom endpoint

<!-- TODO: translate body -->

<a id="section-1-1"></a>

### View Custom Endpoint List

<!-- TODO: translate body -->

<a id="section-1-1-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-1-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-1-2"></a>

### Get a Custom Endpoint

<!-- TODO: translate body -->

<a id="section-1-2-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-2-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-1-3"></a>

### Create Custom Endpoint

<!-- TODO: translate body -->

<a id="section-1-3-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-3-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-1-4"></a>

### Modify Custom Endpoint

<!-- TODO: translate body -->

<a id="section-1-4-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-4-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-1-5"></a>

### Delete Custom Endpoint

<!-- TODO: translate body -->

<a id="section-1-5-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-5-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-1-6"></a>

### Reissue the Service Name

<!-- TODO: translate body -->

<a id="section-1-6-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-1-6-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-2"></a>

## Allowed Projects

<!-- TODO: translate body -->

<a id="section-2-1"></a>

### View Allowed Project List

<!-- TODO: translate body -->

<a id="section-2-1-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-2-1-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-2-2"></a>

### View Allowed Projects

<!-- TODO: translate body -->

<a id="section-2-2-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-2-2-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-2-3"></a>

### Create an Allowed Project

<!-- TODO: translate body -->

<a id="section-2-3-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-2-3-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-2-4"></a>

### Modify Allowed Projects

<!-- TODO: translate body -->

<a id="section-2-4-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-2-4-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-2-5"></a>

### Delete an Allowed Project

<!-- TODO: translate body -->

<a id="section-2-5-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-2-5-2"></a>

#### Response

<!-- TODO: translate body -->

<a id="section-3"></a>

## Usage Status

<!-- TODO: translate body -->

<a id="section-3-1"></a>

### View Usage Status List

<!-- TODO: translate body -->

<a id="section-3-1-1"></a>

#### Request

<!-- TODO: translate body -->

<a id="section-3-1-2"></a>

#### Response

<!-- TODO: translate body -->

