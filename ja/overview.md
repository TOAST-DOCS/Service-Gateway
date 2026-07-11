<!-- pre-align:aligned sig=321428a4bf12 -->

<a id="network-service-gateway-overview"></a>
## Network > Service Gateway > 概要 { #network-service-gateway-overview }

**Service Gateway**サービスを利用すると**Floating IP**を使用せず、トラフィックがインターネットを経由しなくても**VPC**外部のNHN Cloudの**サービス**を利用できます。**サービスゲートウェイ作成**時に選択された**サービス**と自動的に割り当てられたIPは1:1接続関係を維持し、**VPC**では**サービスゲートウェイ**のIPを利用してNHN Cloudの内部ネットワークを経由して対象**サービス**を安全に利用できます。

<a id="main-features"></a>
### 主な機能 { #main-features }

* VPCからインターネットを経由せずにサービスゲートウェイで提供するNHN Cloudのサービスに接続できます。
* サービスゲートウェイ作成時にサービスリストに提供されるサービスのみ利用可能です。
* サービスゲートウェイのIPアドレスはサービスゲートウェイ作成時に選択されたサービスと1:1で接続されます。
* VPCのVM InstanceからサービスゲートウェイのIPアドレスに通信すると、サービスゲートウェイに接続されたサービスと通信されます。
* 現在は韓国(パンギョ)、韓国(ピョンチョン)リージョンにのみ提供されます。今後、他のリージョンもサポートする予定です。

<a id="provided-services"></a>
### 提供サービス { #provided-services }

VPCのVM Instanceからインターネットを経由せずにNHN Cloudのサービスにアクセスする必要がある場合は、サービスゲートウェイで提供されるサービスを選択してサービスゲートウェイを作成します。
詳細な使い方は[Service Gateway > コンソール使用ガイド](/Network/Service%20Gateway/ja/console-guide/)を参照してください。

提供サービス提供[**サービスエンドポイント**](/Network/Service%20Gateway/ja/service-endpoint/)ポイントをご覧ください。提供されるサービスは徐々に拡大していく予定です。
