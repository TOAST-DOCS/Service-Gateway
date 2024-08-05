## Network > Service Gateway > 連動サービスエンドポイント

サービスゲートウェイを利用してNHN Cloudの内部ネットワークと通信できるサービスリスト及び各サービスのエンドポイントです。

### リージョンコード

* リージョンサービスはリージョンごとにエンドポイントアドレスが異なるため、`{region code}`に下記のリージョンコードを記入する必要があります。

| リージョン | リージョンコード |
| --- | ----- |
| 韓国(パンギョ) | kr1 |
| 韓国(ピョンチョン) | kr2 |
| 日本(東京) | jp1 |
| 米国(カリフォルニア) | us1 |

### サービスゲートウェイ連動サービス

* 下記のサービスでサービスゲートウェイを作成すると、インターネットを経由せず、NHN Cloud内部ネットワークにアクセスできます。
    * サービスゲートを作成する方法は[Service Gateway > コンソール使用ガイド](https://docs.nhncloud.com/ko/Network/Service%20Gateway/ko/console-guide/)をご参照ください。
    * 下記に記載されていないサービスについては、[サポート](https://www.nhncloud.com/kr/support/inquiry)にお問い合わせください。
* サービスゲートウェイを作成できるサービスおよびエンドポイントアドレスです。
    * `/etc/hosts`ファイルにサービスゲートウェイのIPアドレスとアクセスしたいサービスエンドポイントアドレスを追加するとURLで接続できます。
        * 例) <span style="color:rgb(68, 68, 68);">192</span><span style="color:rgb(136, 0, 0);" class="hljs-selector-class">.168.1.42</span><span style="color:rgb(68, 68, 68);"> </span><span style="color:rgb(68, 68, 68);" class="hljs-selector-tag">kr1-api-object-storage</span><span style="color:rgb(136, 0, 0);" class="hljs-selector-class">.nhncloudservice.com</span>

| サービス | <span style="color:rgb(255, 255, 255);">サービスゲートウェイエンドポイント名前</span> | エンドポイントアドレス |
| --- | ------------------ | -------- |
| IaaS API Identity (nhncloudservice.com) | IaaS API Identity (nhncloudservice.com) | <span style="color:rgb(49, 51, 56);">[https://api-identity-infrastructure.nhncloudservice.com](https://api-identity-infrastructure.nhncloudservice.com)</span> |
| IaaS API Key-Manager | IaaS API Key-Manager | <span style="color:rgb(49, 51, 56);">[https://](https://kr1-api-key-manager-infrastructure.nhncloudservice.com)</span>`{region code}`<span style="color:rgb(49, 51, 56);">[-api-key-manager-infrastructure.nhncloudservice.com](https://kr1-api-key-manager-infrastructure.nhncloudservice.com)</span> |
| IaaS API Compute | IaaS API Compute | <span style="color:rgb(49, 51, 56);">[https://](https://kr1-api-instance-infrastructure.nhncloudservice.com)</span>`{region code}`<span style="color:rgb(49, 51, 56);">[-api-instance-infrastructure.nhncloudservice.com](https://kr1-api-instance-infrastructure.nhncloudservice.com)</span> |
| IaaS API Network | IaaS API Network | <span style="color:rgb(49, 51, 56);">[https://](https://kr1-api-network-infrastructure.nhncloudservice.com)</span>`{region code}`<span style="color:rgb(49, 51, 56);">[-api-network-infrastructure.nhncloudservice.com](https://kr1-api-network-infrastructure.nhncloudservice.com)</span> |
| IaaS API Volume v2 | IaaS API Volume v2 | <span style="color:rgb(49, 51, 56);">[https://](https://kr1-api-block-storage-infrastructure.nhncloudservice.com)</span>`{region code}`<span style="color:rgb(49, 51, 56);">[-api-block-storage-infrastructure.nhncloudservice.com](https://kr1-api-block-storage-infrastructure.nhncloudservice.com)</span> |
| IaaS API Container - Infra | IaaS API Container - Infra |  |
| NHN Container Registry(NCR) | NHN Container Registry(NCR)<br>API Gateway | ユーザーレジストリURI<br>[https://](https://kr1-ncr.api.nhncloudservice.com/)`{region code}`[-ncr.api.nhncloudservice.com](https://kr1-ncr.api.nhncloudservice.com/) |
| DNS Plus | API Gateway | <span style="color:rgb(49, 51, 56);">[https://dnsplus.api.nhncloudservice.com](https://dnsplus.api.nhncloudservice.com/)</span> |
| Object Storage | Object Storage | <span style="color:rgb(49, 51, 56);">[https://](https://kr1-api-object-storage.nhncloudservice.com)</span>`{region code}`<span style="color:rgb(49, 51, 56);">[-api-object-storage.nhncloudservice.com](https://kr1-api-object-storage.nhncloudservice.com)</span> |
| RDS for MySQL | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-rds-mysql.api.nhncloudservice.com</span> |
| RDS for MariaDB | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-rds-mariadb.api.nhncloudservice.com</span> |
| Server Security Check | Server Security Check |  |
| Security Monitoring | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-secmon.api.nhncloudservice.com</span> |
| Gamebase | API Gateway | <span style="color:rgb(49, 51, 56);">[https://api-gamebase.nhncloudservice.com](https://api-gamebase.nhncloudservice.com)</span> |
| Launching | API Gateway | [https://launching.api.nhncloudservice.com](https://launching.api.nhncloudservice.com/) |
| CDN | API Gateway | [https://cdn.api.nhncloudservice.com](https://cdn.api.nhncloudservice.com) |
| RCS Bizmessage | API Gateway | [https://rcs-bizmessage.api.nhncloudservice.com](https://rcs-bizmessage.api.nhncloudservice.com) |
| Email | API Gateway | [https://email.api.nhncloudservice.com](https://email.api.nhncloudservice.com) |
| Face Recognition | API Gateway | [https://face-recognition.api.nhncloudservice.com](https://face-recognition.api.nhncloudservice.com) |
| AI Fashion | API Gateway | <span style="color:rgb(49, 51, 56);">[https://api-aifashion.nhncloudservice.com](https://api-aifashion.nhncloudservice.com)</span> |
| OCR | API Gateway | <span style="color:rgb(49, 51, 56);">[https://ocr.api.nhncloudservice.com](https://ocr.api.nhncloudservice.com)</span> |
| Text to Speech | API Gateway | <span style="color:rgb(49, 51, 56);">[https://speech.api.nhncloudservice.com](https://speech.api.nhncloudservice.com)</span> |
| Speech to Text | API Gateway | <span style="color:rgb(49, 51, 56);">[https://speech.api.nhncloudservice.com](https://speech.api.nhncloudservice.com)</span> |
| Pose Estimation | API Gateway | <span style="color:rgb(49, 51, 56);">[https://pose-estimation.api.nhncloudservice.com](https://pose-estimation.api.nhncloudservice.com)</span> |
| Maps | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-maps.api.nhncloudservice.com</span> |
| ROLE | API Gateway | [https://role.api.nhncloudservice.com](https://role.api.nhncloudservice.com) |
| API Gateway | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-apigateway.api.nhncloudservice.com</span> |
| Cloud Search | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-search.api.nhncloudservice.com</span> |
| Autocomplete | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-autocomplete.api.nhncloudservice.com</span> |
| Word Suggestion | API Gateway | [https://word-suggestion.api.nhncloudservice.com](https://word-suggestion.api.nhncloudservice.com/v1.0/appkeys/%7BappKey%7D/word-suggestion/suggestion) |
| Pipeline | API Gateway | <span style="color:rgb(49, 51, 56);">https://</span>`{region code}`<span style="color:rgb(49, 51, 56);">-pipeline.api.nhncloudservice.com/</span> |
| Certificate Manager | API Gateway | [https://certmanager.api.nhncloudservice.com](https://certmanager.api.nhncloudservice.com) |
| CloudTrail | CloudTrail<br>API Gateway | [https://cloud-trail.api.nhncloudservice.com](https://cloud-trail.api.nhncloudservice.com) |
| Resource Watcher | API Gateway | [https://resource-watcher.api.nhncloudservice.com](https://resource-watcher.api.nhncloudservice.com) |
