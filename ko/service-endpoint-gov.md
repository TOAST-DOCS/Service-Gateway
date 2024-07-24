## Network > Service Gateway > 서비스 엔드포인트

서비스 게이트웨이를 이용하여 NHN Cloud 내부 네트워크로 통신할 수 있는 서비스 목록 및 각 서비스별 엔드포인트입니다.

### 리전 코드

* 리전 서비스는 각 리전별로 엔드포인트 주소가 다르므로 `{region code}`에 아래의 리전 코드를 기입해야 합니다.

| 리전 | 리전 코드 |
| --- | ----- |
| 한국(판교) | kr1 |
| 한국(평촌) | kr2 |

### 서비스 게이트웨이 연동 서비스

* 아래 서비스로 서비스 게이트웨이를 생성하면 인터넷을 경유하지 않고, NHN Cloud 내부 네트워크로 접근할 수 있습니다.
    * 서비스 게이트를 생성하는 방법은 [Service Gateway > 콘솔 사용 가이드](https://docs.gov-nhncloud.com/ko/Network/Service%20Gateway/ko/console-guide-gov/)를 참고하시기 바랍니다.
    * 아래 기재되지 않은 서비스는 [고객센터](https://www.gov-nhncloud.com/kr/support/inquiry)로 문의해 주시기 바랍니다.
* 서비스 게이트웨이를 생성할 수 있는 서비스 및 엔드포인트 주소입니다.
    * `/etc/hosts` 파일에 서비스 게이트웨이의 IP 주소와 접근하고자 하는 서비스 엔드포인트 주소를 추가해야 URL로 접속할 수 있습니다.
        * 예시) 192168.1.42 kr1-api-object-storage.nhncloudservice.com

| 서비스 | 서비스 게이트웨이 엔드포인트 이름 | 엔드포인트 주소 |
| --- | ------------------ | -------- |
| IaaS API Identity (nhncloudservice.com) | IaaS API Identity (nhncloudservice.com) | https://api-identity-infrastructure.gov-nhncloudservice.com |
| IaaS API Key-Manager | IaaS API Key-Manager | https://`{region code}`-api-key-manager-infrastructure.gov-nhncloudservice.com |
| IaaS API Compute | IaaS API Compute | https://`{region code}`-api-instance-infrastructure.gov-nhncloudservice.com |
| IaaS API Network | IaaS API Network | https://`{region code}`-api-network-infrastructure.gov-nhncloudservice.com |
| IaaS API Volume v2 | IaaS API Volume v2 | https://`{region code}`api-block-storage-infrastructure.gov-nhncloudservice.com |
| IaaS API Container - Infra | IaaS API Container - Infra | https://`{region code}`-api-kubernetes-infrastructure.gov-nhncloudservice.com |
| NHN Container Registry(NCR) | NHN Container Registry(NCR)<br>API Gateway | 사용자 레지스트리 URI<br>https://`{region code}`-ncr.api.gov-nhncloudservice.com |
| DNS Plus | API Gateway | https://dnsplus.api.gov-nhncloudservice.com |
| Object Storage | Object Storage | https://`{region code}`-api-object-storage.gov-nhncloudservice.com |
| RDS for MySQL | API Gateway | https://`{region code}`-rds-mysql.api.gov-nhncloudservice.com |
| RDS for MariaDB | API Gateway | https://`{region code}`-rds-mariadb.api.gov-nhncloudservice.com |
| Security Monitoring | API Gateway | https://`{region code}`<-secmon.api.gov-nhncloudservice.com |
| CDN | API Gateway | https://cdn.api.gov-nhncloudservice.com |
| API Gateway | API Gateway | https://`{region code}`-apigateway.api.gov-nhncloudservice.com |
| Pipeline | API Gateway | https://`{region code}`-pipeline.api.gov-nhncloudservice.com |
| Certificate Manager | API Gateway | https://certmanager.api.gov-nhncloudservice.com |
| CloudTrail | CloudTrail<br>API Gateway | https://cloud-trail.api.gov-nhncloudservice.com |
| Resource Watcher | API Gateway | https://resource-watcher.api.gov-nhncloudservice.com |