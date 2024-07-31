## Network > Service Gateway > 서비스 엔드포인트

서비스 게이트웨이를 이용하여 NHN Cloud 내부 네트워크로 통신할 수 있는 서비스 목록 및 각 서비스별 엔드포인트입니다.

### 리전 코드

* 리전 서비스는 각 리전별로 엔드포인트 주소가 다르므로 `{region code}`에 아래의 리전 코드를 기입해야 합니다.

| 리전 | 리전 코드 |
| --- | ----- |
| 한국(판교) | kr1 |
| 한국(평촌) | kr2 |
| 일본(도쿄) | jp1 |
| 미국(캘리포니아) | us1 |

### 서비스 게이트웨이 연동 서비스

* 아래 서비스로 서비스 게이트웨이를 생성하면 인터넷을 경유하지 않고, NHN Cloud 내부 네트워크로 접근할 수 있습니다.
    * 서비스 게이트를 생성하는 방법은 [Service Gateway > 콘솔 사용 가이드](/Network/Service%20Gateway/en/console-guide/)를 참고하세요.
    * 아래 기재되지 않은 서비스는 [고객센터](https://www.nhncloud.com/kr/support/inquiry)로 문의하세요.
* 서비스 게이트웨이를 생성할 수 있는 서비스 및 엔드포인트 주소입니다.
    * `/etc/hosts` 파일에 서비스 게이트웨이의 IP 주소와 접근하고자 하는 서비스 엔드포인트 주소를 추가해야 URL로 접속할 수 있습니다.
        * 예시) 192.168.1.42 kr1-api-object-storage.nhncloudservice.com

| 서비스 | 서비스 게이트웨이 엔드포인트 이름 | 엔드포인트 주소 |
| --- | ------------------ | -------- |
| [IaaS API Identity (nhncloudservice.com)](/Compute/Compute/en/identity-api/#token) | IaaS API Identity (nhncloudservice.com) | https://api-identity-infrastructure.nhncloudservice.com |
| [IaaS API Key-Manager](/Network/Load%20Balancer/en/public-api/) | IaaS API Key-Manager | https://{region code}-api-key-manager-infrastructure.nhncloudservice.com |
| [IaaS API Compute](/Compute/Instance/en/public-api/) | IaaS API Compute | https://{region code}-api-instance-infrastructure.nhncloudservice.com |
| [IaaS API Network](/Network/VPC/en/public-api/) | IaaS API Network | https://{region code}-api-network-infrastructure.nhncloudservice.com |
| [IaaS API Volume v2](/Storage/Block%20Storage/en/public-api/) | IaaS API Volume v2 | https://{region code}-api-block-storage-infrastructure.nhncloudservice.com |
| [IaaS API Container - Infra](/Container/NKS/en/public-api/) | IaaS API Container - Infra | https://{region code}-api-kubernetes-infrastructure.nhncloudservice.com |
| [NHN Container Registry(NCR)](/Container/NCR/en/public-api) | NHN Container Registry(NCR)<br>API Gateway | 사용자 레지스트리 URI<br>https://{region code}-ncr.api.nhncloudservice.com |
| [DNS Plus](/Network/DNS%20Plus/en/api-guide/) | API Gateway | https://dnsplus.api.nhncloudservice.com |
| [Object Storage](/Storage/Object%20Storage/en/api-guide/) | Object Storage | https://{region code}-api-object-storage.nhncloudservice.com |
| [RDS for MySQL](/Database/RDS%20for%20MySQL/en/api-guide-v3.0/) | API Gateway | https://{region code}-rds-mysql.api.nhncloudservice.com |
| [RDS for MariaDB](/RDS%20for%20MariaDB/en/api-guide-v3.0/) | API Gateway | https://{region code}-rds-mariadb.api.nhncloudservice.com |
| [Server Security Check](/Security/Server%20Security%20Check/en/Overview/) | Server Security Check | https://api-serversecuritycheck.nhncloudservice.com |
| [Security Monitoring](/Security/Security%20Monitoring/en/api-guide-v1.1/) | API Gateway | https://{region code}-secmon.api.nhncloudservice.com |
| [Gamebase](/Game/Gamebase/en/api-guide/) | API Gateway | https://api-gamebase.nhncloudservice.com|
| [Launching](/Game/Launching/en/api-guide/) | API Gateway | https://launching.api.nhncloudservice.com |
| [CDN](/Contents%20Delivery/CDN/en/api-guide-v2.0/) | API Gateway | https://cdn.api.nhncloudservice.com |
| [RCS Bizmessage](/Notification/RCS%20Bizmessage/en/api-guide/) | API Gateway | https://rcs-bizmessage.api.nhncloudservice.com |
| [Email](/Notification/Email/en/api-guide/) | API Gateway | https://email.api.nhncloudservice.com |
| [Face Recognition](/AI%20Service/Face%20Recognition/en/api-guide-v2.0/) | API Gateway | https://face-recognition.api.nhncloudservice.com |
| [AI Fashion](/AI%20Service/AI%20Fashion/en/api-guide-v2.0/) | API Gateway | https://api-aifashion.nhncloudservice.com |
| [OCR](/AI%20Service/OCR/en/general-ocr-api-guide/) | API Gateway | https://ocr.api.nhncloudservice.com |
| [Text to Speech](/AI%20Service/Text%20to%20Speech/en/api-guide/) | API Gateway | https://speech.api.nhncloudservice.com |
| [Speech to Text](/AI%20Service/Speech%20to%20Text/en/api-guide/) | API Gateway | https://speech.api.nhncloudservice.com |
| [Pose Estimation](/AI%20Service/Pose%20Estimation/en/api-guide/) | API Gateway | https://pose-estimation.api.nhncloudservice.com |
| [Maps](/Application%20Service/Maps/en/api-guide-v3.0/) | API Gateway | https://{region code}-maps.api.nhncloudservice.com |
| [ROLE](/Application%20Service/ROLE/en/api-v3-guide/) | API Gateway | https://role.api.nhncloudservice.com |
| [API Gateway](A/pplication%20Service/API%20Gateway/en/api-guide-v1.0/) | API Gateway | https://{region code}-apigateway.api.nhncloudservice.com |
| [Cloud Search](/Search/Cloud%20Search/en/api-guide/api-v2.0-guide/) | API Gateway | https://{region code}-search.api.nhncloudservice.com |
| [Autocomplete](/Search/Autocomplete/en/api-guide/api-v2.0-guide/) | API Gateway | https://{region code}-autocomplete.api.nhncloudservice.com |
| [Word Suggestion](/Search/Word%20Suggestion/en/api-guide/) | API Gateway | https://word-suggestion.api.nhncloudservice.com |
| [Pipeline](/Dev%20Tools/Pipeline/en/api-guide/) | API Gateway | https://{region code}-pipeline.api.nhncloudservice.com |
| [Certificate Manager](/Management/Certificate%20Manager/en/api-guide-v1.1/) | API Gateway | https://certmanager.api.nhncloudservice.com |
| [CloudTrail](/Governance%20&%20Audit/CloudTrail/en/api-guide/) | CloudTrail<br>API Gateway | https://cloud-trail.api.nhncloudservice.com |
| [Resource Watcher](/Governance%20&%20Audit/Resource%20Watcher/en/api-v2-guide/) | API Gateway | https://resource-watcher.api.nhncloudservice.com |
