## Network > Service Gateway > Service Endpoint

A list of services that can communicate with the NHN Cloud internal network using Service Gateway and the endpoints for each service.

### Region Code

* Region services have different endpoint addresses for each region, so you must fill in the region code below `{region code}`.

| Region | Region Code |
| --- | ----- |
| Korea (Pangyo) | kr1 |
| Korea (Pyeongchon) | kr2 |
| Japan (Tokyo) | jp1 |
| United States (California) | us1 |

### Service Gateway Integration Services

* By creating a service gateway with the services below, you can access the internal network of NHN Cloud without going through the Internet.
    * To create a service gateway, see the [Service Gateway > Console User Guide](/Network/Service%20Gateway/zh/console-guide/).
    * For services not listed below, contact [Customer Center](https://www.nhncloud.com/kr/support/inquiry).
* The service and endpoint addresses for which you can create a service gateway.
    * In the `/etc/hosts` file, you must add the IP address of the service gateway and the service endpoint address you want to access to the URL.
        * Example) 192.168.1.42 kr1-api-object-storage.nhncloudservice.com

| Service | Service Gateway endpoint name | Endpoint address |
| --- | ------------------ | -------- |
| [IaaS API Identity (nhncloudservice.com)](/Compute/Compute/zh/identity-api/#token) | IaaS API Identity (nhncloudservice.com) | https://api-identity-infrastructure.nhncloudservice.com |
| [IaaS API Key-Manager](/Network/Load%20Balancer/zh/public-api/) | IaaS API Key-Manager | https://{region code}-api-key-manager-infrastructure.nhncloudservice.com |
| [IaaS API Compute](/Compute/Instance/zh/public-api/) | IaaS API Compute | https://{region code}-api-instance-infrastructure.nhncloudservice.com |
| [IaaS API Network](/Network/VPC/zh/public-api/) | IaaS API Network | https://{region code}-api-network-infrastructure.nhncloudservice.com |
| [IaaS API Volume v2](/Storage/Block%20Storage/zh/public-api/) | IaaS API Volume v2 | https://{region code}-api-block-storage-infrastructure.nhncloudservice.com |
| [IaaS API Container - Infra](/Container/NKS/zh/public-api/) | IaaS API Container - Infra | https://{region code}-api-kubernetes-infrastructure.nhncloudservice.com |
| [NHN Container Registry(NCR)](/Container/NCR/zh/public-api) | NHN Container Registry(NCR)<br>API Gateway | User registry URI<br>https://{region code}-ncr.api.nhncloudservice.com |
| [NHN Container Service(NCS)](/Container/NCS/zh/public-api) | API Gateway | https://{region code}-ncs.api.nhncloudservice.com |
| [DNS Plus](/Network/DNS%20Plus/zh/api-guide/) | API Gateway | https://dnsplus.api.nhncloudservice.com |
| [Object Storage](/Storage/Object%20Storage/zh/api-guide/) | Object Storage | https://{region code}-api-object-storage.nhncloudservice.com |
| [RDS for MySQL](/Database/RDS%20for%20MySQL/zh/api-guide-v3.0/) | API Gateway | https://{region code}-rds-mysql.api.nhncloudservice.com |
| [RDS for PostgreSQL](/Database/RDS%20for%20PostgreSQL/zh/api-guide-v1.0/) | API Gateway | https://{region code}-rds-postgres.api.nhncloudservice.com |
| [RDS for MariaDB](/Database/RDS%20for%20MariaDB/zh/api-guide-v3.0/) | API Gateway | https://{region code}-rds-mariadb.api.nhncloudservice.com |
| [Server Security Check](/Security/Server%20Security%20Check/zh/Overview/) | Server Security Check | https://api-serversecuritycheck.nhncloudservice.com |
| [Security Monitoring](/Security/Security%20Monitoring/zh/api-guide-v1.1/) | API Gateway | https://{region code}-secmon.api.nhncloudservice.com |
| [Gamebase](/Game/Gamebase/zh/api-guide/) | API Gateway | https://api-gamebase.nhncloudservice.com|
| [Launching](/Game/Launching/zh/api-guide/) | API Gateway | https://launching.api.nhncloudservice.com |
| [CDN](/Contents%20Delivery/CDN/zh/api-guide-v2.0/) | API Gateway | https://cdn.api.nhncloudservice.com |
| [RCS Bizmessage](/Notification/RCS%20Bizmessage/zh/api-guide/) | API Gateway | https://rcs-bizmessage.api.nhncloudservice.com |
| [Email](/Notification/Email/zh/api-guide/) | API Gateway | https://email.api.nhncloudservice.com |
| [Face Recognition](/AI%20Service/Face%20Recognition/zh/api-guide-v2.0/) | API Gateway | https://face-recognition.api.nhncloudservice.com |
| [AI Fashion](/AI%20Service/AI%20Fashion/zh/api-guide-v2.0/) | API Gateway | https://api-aifashion.nhncloudservice.com |
| [OCR](/AI%20Service/OCR/zh/general-ocr-api-guide/) | API Gateway | https://ocr.api.nhncloudservice.com |
| [Text to Speech](/AI%20Service/Text%20to%20Speech/zh/api-guide/) | API Gateway | https://speech.api.nhncloudservice.com |
| [Speech to Text](/AI%20Service/Speech%20to%20Text/zh/api-guide/) | API Gateway | https://speech.api.nhncloudservice.com |
| [Maps](/Application%20Service/Maps/zh/api-guide-v3.0/) | API Gateway | https://{region code}-maps.api.nhncloudservice.com |
| [ROLE](/Application%20Service/ROLE/zh/api-v3-guide/) | API Gateway | https://role.api.nhncloudservice.com |
| [API Gateway](/Application%20Service/API%20Gateway/zh/api-guide-v1.0/) | API Gateway | https://{region code}-apigateway.api.nhncloudservice.com |
| [Cloud Search](/Search/Cloud%20Search/zh/api-guide/api-v2.0-guide/) | API Gateway | https://{region code}-search.api.nhncloudservice.com |
| [Autocomplete](/Search/Autocomplete/zh/api-guide/api-v2.0-guide/) | API Gateway | https://{region code}-autocomplete.api.nhncloudservice.com |
| [Log & Crash Search](/Data%20&%20Analytics/Log%20&%20Crash%20Search/zh/api-guide/) | Log & Crash Search | https://api-logncrash.nhncloudservice.com |
| [Pipeline](/Dev%20Tools/Pipeline/zh/api-guide/) | API Gateway | https://{region code}-pipeline.api.nhncloudservice.com |
| [Certificate Manager](/Management/Certificate%20Manager/zh/api-guide-v1.1/) | API Gateway | https://certmanager.api.nhncloudservice.com |
| [CloudTrail](/Governance%20&%20Audit/CloudTrail/zh/api-guide/) | CloudTrail<br>API Gateway | https://cloud-trail.api.nhncloudservice.com |
| [Resource Watcher](/Governance%20&%20Audit/Resource%20Watcher/zh/api-v2-guide/) | API Gateway | https://resource-watcher.api.nhncloudservice.com |
| [API Authentication](/nhncloud/zh/public-api/api-authentication/) |  API Gateway | https://oauth.api.nhncloudservice.com | 
| [Framework API](/nhncloud/zh/public-api/framework-api/) |  API Gateway | https://core.api.nhncloudservice.com | 