## Network > Service Gateway > 서비스 엔드포인트

서비스 게이트웨이를 이용하여 NHN Cloud 내부 네트워크로 통신할 수 있는 서비스 목록 및 각 서비스별 엔드포인트입니다.

### 서비스 게이트웨이 연동 서비스

* 아래 서비스로 서비스 게이트웨이를 생성하면 인터넷을 경유하지 않고, NHN Cloud 내부 네트워크로 접근할 수 있습니다.
    * 서비스 게이트를 생성하는 방법은 [Service Gateway > 콘솔 사용 가이드](https://docs.gncloud.go.kr/ko/Network/Service%20Gateway/ko/console-guide-gov/)를 참고하시기 바랍니다.
    * 아래 기재되지 않은 서비스는 [고객센터](https://gncloud.go.kr/kr/support/inquiry)로 문의해 주시기 바랍니다.
* 서비스 게이트웨이를 생성할 수 있는 서비스 및 엔드포인트 주소입니다.
    * `/etc/hosts` 파일에 서비스 게이트웨이의 IP 주소와 접근하고자 하는 서비스 엔드포인트 주소를 추가해야 URL로 접속할 수 있습니다.
        * 예시) 192168.1.42 kr1-api-object-storage.nhncloudservice.com

| 서비스 | 서비스 게이트웨이 엔드포인트 이름 | 엔드포인트 주소 |
| --- | ------------------ | -------- |
| IaaS API Identity (nhncloudservice.com) | IaaS API Identity (nhncloudservice.com) | https://api-identity-infrastructure.gncloud.go.kr |
| IaaS API Key-Manager | IaaS API Key-Manager | https://kr1-api-key-manager-infrastructure.gncloud.go.kr |
| IaaS API Compute | IaaS API Compute | https://kr1api-instance-infrastructure.gncloud.go.kr |
| IaaS API Network | IaaS API Network | https://kr1-api-network-infrastructure.gncloud.go.kr |
| IaaS API Volume v2 | IaaS API Volume v2 | https://kr1api-block-storage-infrastructure.gncloud.go.kr |
| IaaS API Container - Infra | IaaS API Container - Infra | https://kr1-api-kubernetes-infrastructure.gncloud.go.kr |
| NHN Container Registry(NCR) | NHN Container Registry(NCR)<br>API Gateway | 사용자 레지스트리 URI<br>https://`{region code}`-ncr.api.gncloud.go.kr |
| Object Storage | Object Storage | https://kr1-api-object-storage.gncloud.go.kr |
| RDS for MySQL | API Gateway | https://kr1-rds-mysql.api.gncloud.go.kr |
| CloudTrail | CloudTrail<br>API Gateway | https://cloud-trail.api.gncloud.go.kr |