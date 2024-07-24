## Network > Service Gateway > 연동 서비스 엔드포인트

서비스 게이트웨이를 이용하여 NHN Cloud 내부 네트워크로 통신할 수 있는 서비스 목록 및 각 서비스별 엔드포인트입니다.

### 서비스 게이트웨이 연동 서비스

* 아래 서비스로 서비스 게이트웨이를 생성하면 인터넷을 경유하지 않고, NHN Cloud 내부 네트워크로 접근할 수 있습니다.
    * 서비스 게이트를 생성하는 방법은 [Service Gateway > 콘솔 사용 가이드](https://docs.nhncloud.com/ko/Network/Service%20Gateway/ko/console-guide/)를 참고하시기 바랍니다.
    * 아래 기재되지 않은 서비스는 [고객센터](https://www.nhncloud.com/kr/support/inquiry)로 문의해 주시기 바랍니다.
* 서비스 게이트웨이를 생성할 수 있는 서비스 및 엔드포인트 주소입니다.
    * `/etc/hosts` 파일에 서비스 게이트웨이의 IP 주소와 접근하고자 하는 서비스 엔드포인트 주소를 추가해야 URL로 접속할 수 있습니다.
        * 예시) <span style="color:rgb(68, 68, 68);">192</span><span style="color:rgb(136, 0, 0);" class="hljs-selector-class">.168.1.42</span><span style="color:rgb(68, 68, 68);"> </span><span style="color:rgb(68, 68, 68);" class="hljs-selector-tag">kr1-api-object-storage</span><span style="color:rgb(136, 0, 0);" class="hljs-selector-class">.nhncloudservice.com</span>

