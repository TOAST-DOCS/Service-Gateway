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
    * 서비스 게이트를 생성하는 방법은 [Service Gateway > 콘솔 사용 가이드](https://docs.nhncloud.com/ko/Network/Service%20Gateway/ko/console-guide/)를 참고하시기 바랍니다.
    * 아래 기재되지 않은 서비스는 [고객센터](https://www.nhncloud.com/kr/support/inquiry)로 문의해 주시기 바랍니다.
* 서비스 게이트웨이를 생성할 수 있는 서비스 및 엔드포인트 주소입니다.
    * `/etc/hosts` 파일에 서비스 게이트웨이의 IP 주소와 접근하고자 하는 서비스 엔드포인트 주소를 추가해야 URL로 접속할 수 있습니다.
        * 예시) 192.168.1.42 kr1-api-object-storage.nhncloudservice.com

| 서비스 | 서비스 게이트웨이 엔드포인트 이름 | 엔드포인트 주소 |
| --- | ------------------ | -------- |
| IaaS API Identity (nhncloudservice.com) | IaaS API Identity (nhncloudservice.com) | https://api-identity-infrastructure.nhncloudservice.com |
| IaaS API Key-Manager | IaaS API Key-Manager | https://{region code}-api-key-manager-infrastructure.nhncloudservice.com |
| IaaS API Compute | IaaS API Compute | https://{region code}-api-instance-infrastructure.nhncloudservice.com |
| IaaS API Network | IaaS API Network | https://{region code}-api-network-infrastructure.nhncloudservice.com |
| IaaS API Volume v2 | IaaS API Volume v2 | https://{region code}-api-block-storage-infrastructure.nhncloudservice.com |
| IaaS API Container - Infra | IaaS API Container - Infra | https://{region code}-api-kubernetes-infrastructure.nhncloudservice.com |
| NHN Container Registry(NCR) | NHN Container Registry(NCR)<br>API Gateway | 사용자 레지스트리 URI<br>https://{region code}-ncr.api.nhncloudservice.com |
| DNS Plus | API Gateway | https://dnsplus.api.nhncloudservice.com |
| Object Storage | Object Storage | https://{region code}-api-object-storage.nhncloudservice.com |
| RDS for MySQL | API Gateway | https://{region code}-rds-mysql.api.nhncloudservice.com |
| RDS for MariaDB | API Gateway | https://{region code}-rds-mariadb.api.nhncloudservice.com |
| Server Security Check | Server Security Check | https://api-serversecuritycheck.nhncloudservice.com |
| Security Monitoring | API Gateway | https://{region code}-secmon.api.nhncloudservice.com |
| Gamebase | API Gateway | https://api-gamebase.nhncloudservice.com|
| Launching | API Gateway | https://launching.api.nhncloudservice.com |
| CDN | API Gateway | https://cdn.api.nhncloudservice.com |
| RCS Bizmessage | API Gateway | https://rcs-bizmessage.api.nhncloudservice.com |
| Email | API Gateway | https://email.api.nhncloudservice.com |
| Face Recognition | API Gateway | https://face-recognition.api.nhncloudservice.com |
| AI Fashion | API Gateway | https://api-aifashion.nhncloudservice.com |
| OCR | API Gateway | https://ocr.api.nhncloudservice.com |
| Text to Speech | API Gateway | https://speech.api.nhncloudservice.com |
| Speech to Text | API Gateway | https://speech.api.nhncloudservice.com |
| Pose Estimation | API Gateway | https://pose-estimation.api.nhncloudservice.com |
| Maps | API Gateway | https://{region code}-maps.api.nhncloudservice.com |
| ROLE | API Gateway | https://role.api.nhncloudservice.com |
| API Gateway | API Gateway | https://{region code}-apigateway.api.nhncloudservice.com |
| Cloud Search | API Gateway | https://{region code}-search.api.nhncloudservice.com |
| Autocomplete | API Gateway | https://{region code}-autocomplete.api.nhncloudservice.com |
| Word Suggestion | API Gateway | https://word-suggestion.api.nhncloudservice.com |
| Pipeline | API Gateway | https://{region code}-pipeline.api.nhncloudservice.com |
| Certificate Manager | API Gateway | https://certmanager.api.nhncloudservice.com |
| CloudTrail | CloudTrail<br>API Gateway | https://cloud-trail.api.nhncloudservice.com |
| Resource Watcher | API Gateway | https://resource-watcher.api.nhncloudservice.com |
