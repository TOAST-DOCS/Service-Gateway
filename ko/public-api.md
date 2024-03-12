
## Network > Service Gateway > API v2 가이드

API를 사용하려면 API 엔드포인트와 토큰 등이 필요합니다. [API 사용 준비](/Compute/Compute/ko/identity-api/)를 참고하여 API 사용에 필요한 정보를 준비합니다.

트랜짓 허브 API는 `network` 타입 엔드포인트를 이용합니다. 정확한 엔드포인트는 토큰 발급 응답의 `serviceCatalog`를 참조합니다.

| 타입 | 리전 | 엔드포인트 |
|---|---|---|
| network | 한국(판교) 리전<br>한국(평촌) 리전 | https://kr1-api-network-infrastructure.nhncloudservice.com<br>https://kr2-api-network-infrastructure.nhncloudservice.com |

API 응답에 가이드에 명시되지 않은 필드가 나타날 수 있습니다. 이런 필드는 NHN Cloud 내부 용도로 사용되며 사전 공지 없이 변경될 수 있으므로 사용하지 않습니다.

## 서비스 게이트웨이

### 서비스 게이트웨이 목록 보기

```
GET /v2.0/gateways/servicegateways
X-Auth-Token: {tokenId}
```

#### 요청
이 API는 요청 본문을 요구하지 않습니다.

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| id | Query | UUID | - | 조회할 서비스 게이트웨이 ID |
| name | Query | String | - | 조회할 서비스 게이트웨이 이름 |


#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| servicegateways | Body | Array | 서비스 게이트웨이 정보 객체 목록 |
| servicegateways.id | Body | UUID | 서비스 게이트웨이 ID |
| servicegateways.name | Body | String | 서비스 게이트웨이 이름 |
| servicegateways.port_id | Body | String | 포트 ID |
| servicegateways.tenant_id | Body | String | 테넌트 ID |
| servicegateways.network_id | Body | UUID | VPC ID |
| servicegateways.subnet_id | Body | UUID | Subnet ID |
| servicegateways.fixed_ip | Body | String | 서비스 게이트웨이 IP 주소 |
| servicegateways.service_endpoint_id | Body | UUID | 서비스 엔드포인트 ID |
| servicegateways.description | Body | String | 서비스 게이트웨이 설명 |

<details><summary>예시</summary>

```json
{
  "servicegateways": [
    {
      "status": "AVAILABLE",
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
### 서비스 게이퉤이 보기

```
GET /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

#### 요청
이 API는 요청 본문을 요구하지 않습니다.

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| serviceGatewayId | URL | UUID | O | 서비스 게이트웨이 ID |

#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| servicegateways | Body | Object | 서비스 게이트웨이 정보 객체 목록 |
| servicegateways.id | Body | UUID | 서비스 게이트웨이 ID |
| servicegateways.name | Body | String | 서비스 게이트웨이 이름 |
| servicegateways.port_id | Body | String | 포트 ID |
| servicegateways.tenant_id | Body | String | 테넌트 ID |
| servicegateways.network_id | Body | UUID | VPC ID |
| servicegateways.subnet_id | Body | UUID | Subnet ID |
| servicegateways.fixed_ip | Body | String | 서비스 게이트웨이 IP 주소 |
| servicegateways.service_endpoint_id | Body | UUID | 서비스 엔드포인트 ID |
| servicegateways.domain_names | Body | Array | 서비스 API 엔드포인트 도메인 네임 스트링 목록 |
| servicegateways.description | Body | String | 서비스 게이트웨이 설명 |

<details><summary>예시</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "description": "",
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "domain_names": [
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
### 서비스 게이트웨이 생성하기

```
POST /v2.0/gateways/servicegateways
X-Auth-Token: {tokenId}
```

#### 요청

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| servicegateway | Body | Object | O | 서비스 게이트웨이 정보 객체 |
| servicegateway.name | Body | String | - | 서비스 게이트웨이 이름 |
| servicegateway.description | Body | String | - | 서비스 게이트웨이 설명 |
| servicegateway.network_id | Body | UUID | O | VPC ID |
| servicegateway.subnet_id | Body | UUID | O | Subnet ID |
| servicegateway.service_endpoint_id | Body | UUID | O | 서비스 엔드포인트 ID |




<details><summary>예시</summary>

```json
{
  "servicegateway": {
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "service_endpoint_id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5",
    "name": "sgw_test",
    "description": "test"
  }
}
```
</details>

#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| servicegateways | Body | Object | 서비스 게이트웨이 정보 객체 목록 |
| servicegateways.id | Body | UUID | 서비스 게이트웨이 ID |
| servicegateways.name | Body | String | 서비스 게이트웨이 이름 |
| servicegateways.port_id | Body | String | 포트 ID |
| servicegateways.tenant_id | Body | String | 테넌트 ID |
| servicegateways.network_id | Body | UUID | VPC ID |
| servicegateways.subnet_id | Body | UUID | Subnet ID |
| servicegateways.fixed_ip | Body | String | 서비스 게이트웨이 IP 주소 |
| servicegateways.service_endpoint_id | Body | UUID | 서비스 엔드포인트 ID |
| servicegateways.domain_names | Body | Array | 서비스 API 엔드포인트 도메인 네임 스트링 목록 |
| servicegateways.description | Body | String | 서비스 게이트웨이 설명 |


<details><summary>예시</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "description": "",
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "domain_names": [
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
### 서비스 게이트웨이 수정하기

```
PUT /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

#### 요청

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| serviceGatewayId | URL | UUID | O | 서비스 게이트웨이 ID |
| servicegateway | Body | Object | O | 서비스 게이트웨이 정보 객체 |
| servicegateway.name | Body | String | - | 서비스 게이트웨이 이름 |
| servicegateway.description | Body | String | - | 서비스 게이트웨이 설명 |

<details><summary>예시</summary>

```json
{
  "servicegateway": {
    "name": "sgw_test1",
    "description": "test1"
  }
}
```
</details>

#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| servicegateways | Body | Object | 서비스 게이트웨이 정보 객체 목록 |
| servicegateways.id | Body | UUID | 서비스 게이트웨이 ID |
| servicegateways.name | Body | String | 서비스 게이트웨이 이름 |
| servicegateways.port_id | Body | String | 포트 ID |
| servicegateways.tenant_id | Body | String | 테넌트 ID |
| servicegateways.network_id | Body | UUID | VPC ID |
| servicegateways.subnet_id | Body | UUID | Subnet ID |
| servicegateways.fixed_ip | Body | String | 서비스 게이트웨이 IP 주소 |
| servicegateways.service_endpoint_id | Body | UUID | 서비스 엔드포인트 ID |
| servicegateways.domain_names | Body | Array | 서비스 API 엔드포인트 도메인 네임 스트링 목록 |
| servicegateways.description | Body | String | 서비스 게이트웨이 설명 |


<details><summary>예시</summary>

```json
{
  "servicegateway": {
    "status": "AVAILABLE",
    "description": "test1",
    "network_id": "55529e1d-c6ee-4be8-baa9-2b6546667e6d",
    "tenant_id": "302406c4a1d44b2cb2bc07a652c0b202",
    "fixed_ip": "192.168.0.82",
    "subnet_id": "72d9d6e0-3ee2-4287-bcf9-be45a8422ff1",
    "domain_names": [
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
### 서비스 게이트웨이 삭제하기

```
DELETE /v2.0/gateways/servicegateways/{serviceGatewayId}
X-Auth-Token: {tokenId}
```

#### 요청
이 API는 요청 본문을 요구하지 않습니다.

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| serviceGatewayId | URL | UUID | O | 서비스 게이트웨이 ID |


#### 응답
이 API는 응답 본문을 반환하지 않습니다.










## 서비스 엔드포인트

### 서비스 엔드포인트 보기

```
GET /v2.0/gateways/serviceendpoints/
X-Auth-Token: {tokenId}
```

#### 요청
이 API는 요청 본문을 요구하지 않습니다.

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| id | Query | UUID | - | 조회할 서비스 엔드포인트 ID |
| display_name | Query | UUID | - | 조회할 서비스 엔드포인트 이름 |



#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| serviceendpoints | Body | Array | 서비스 엔드포인트 정보 객체 목록 |
| serviceendpoints.id | Body | UUID | 서비스 엔드포인트 ID |
| serviceendpoints.display_name | Body | String | 콘솔에 출력되는 서비스 엔드포인트 이름 |
| serviceendpoints.description | Body | String | 서비스 엔드포인트 설명 |

<details><summary>예시</summary>

```json
{
  "serviceendpoints": [
    {
      "display_name": "Object Storage",
      "description": "",
      "name": "OBS",
      "id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5"
    }
  ]
}
```
</details>

---
### 서비스 엔드포인트 보기

```
GET /v2.0/gateways/serviceendpoints/{seerviceEndpointId}
X-Auth-Token: {tokenId}
```

#### 요청
이 API는 요청 본문을 요구하지 않습니다.

| 이름 | 종류 | 형식 | 필수 | 설명 |
|---|---|---|---|---|
| tokenId | Header | String | O | 토큰 ID |
| serviceEndpointId | URL | UUID | O | 서비스 엔드포인트 ID |

#### 응답

| 이름 | 종류 | 형식 | 설명 |
|---|---|---|---|
| serviceendpoints | Body | Object | 서비스 엔드포인트 정보 객체  |
| serviceendpoints.id | Body | UUID | 서비스 엔드포인트 ID |
| serviceendpoints.display_name | Body | String | 콘솔에 출력되는 서비스 엔드포인트 이름 |
| serviceendpoints.description | Body | String | 서비스 엔드포인트 설명 |

<details><summary>예시</summary>

```json
{
  "serviceendpoint": {
      "display_name": "Object Storage",
      "description": "",
      "name": "OBS",
      "id": "7ba5b6e7-d871-43d3-90d2-7e2beecaaae5"
  }
}
```
</details>

---
