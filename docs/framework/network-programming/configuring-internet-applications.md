---
title: "인터넷 응용 프로그램 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "인터넷 리소스 다운로드, 기본 프록시"
  - "데이터 보내기, 기본 프록시"
  - "데이터 받기, 기본 프록시"
  - "인터넷 리소스 다운로드, 인터넷 응용 프로그램 구성"
  - "프로토콜별 모듈"
  - "사용자 지정 인증 모듈"
  - "데이터 받기, 인터넷 응용 프로그램 구성"
  - "구성 설정[.NET Framework], 인터넷 응용 프로그램"
  - "인터넷에서 데이터 요청, 인터넷 응용 프로그램 구성"
  - "인터넷에서 데이터 요청, 기본 프록시"
  - "인터넷 요청에 응답, 기본 프록시"
  - "인터넷, 인터넷 응용 프로그램 구성"
  - "인터넷 요청에 응답, 인터넷 응용 프로그램 구성"
  - "기본 프록시"
  - "네트워크 리소스, 기본 프록시"
  - "데이터 보내기, 인터넷 응용 프로그램 구성"
  - "네트워크 리소스, 인터넷 응용 프로그램 구성"
  - "인터넷, 기본 프록시"
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 인터넷 응용 프로그램 구성
[\<system.Net\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 구성 요소 응용 프로그램에 대 한 네트워크 구성 정보를 포함 합니다.  사용 하는 [\<system.Net\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 요소, 프록시 서버 설정, 연결 관리 매개 변수 설정 및 사용자 지정 인증 및 요청 모듈을 응용 프로그램에 포함 합니다.  
  
 [\<defaultProxy\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 요소를 반환 하는 프록시 서버 정의 `GlobalProxySelection` 클래스.  모든 <xref:System.Net.HttpWebRequest> 는 없는 자체 <xref:System.Net.HttpWebRequest.Proxy%2A> 속성을 특정 값으로 설정 합니다. 기본 프록시를 사용 합니다.  프록시 주소를 설정 하는 것 외에도 프록시를 사용 하지 않습니다 서버 주소 목록을 만들 수 있습니다 및 프록시 로컬 주소를 사용할 수 있음을 나타낼 수 있습니다.  
  
 두 번째 기록 우선 순위가 구성 설정으로 Microsoft Internet Explorer 설정을 결합 하는 것이 중요 합니다.  
  
 다음 예제에서는 기본 프록시 서버 주소를 http:\/\/proxyserver 설정, 프록시 로컬 주소를 사용 해야 지정 contoso.com 도메인에 있는 서버에 대 한 모든 요청이 프록시를 무시 해야 함을 나타냅니다.  
  
```  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 사용 된 [\<connectionManagement\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) 특정 서버 또는 다른 모든 서버에 연결할 수 있는 영구 연결 수를 구성 하는 요소입니다.  다음 예제에서는 서버 www.contoso.com에 영구 연결을 두 개, 네 개의 영구 연결을 서버에 IP 주소 192.168.1.2 다른 모든 서버에 영구 연결을 하나 사용 하는 응용 프로그램을 구성 합니다.  
  
```  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 사용자 지정 인증 모듈 구성 되는 [\<authenticationModules\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) 요소.  사용자 지정 인증 모듈을 구현 해야 하는 <xref:System.Net.IAuthenticationModule> 인터페이스.  
  
 다음 예제에서는 사용자 지정 인증 모듈을 구성합니다.  
  
```  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 사용할 수 있는 [\<webRequestModules\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) 인터넷 리소스에서 요청 정보를 사용자 지정 프로토콜 고유 모듈을 사용 하 여 응용 프로그램을 구성 하는 요소.  지정 된 모듈을 구현 해야는 <xref:System.Net.IWebRequestCreate> 인터페이스.  다음 예제와 같이 구성 파일에서 사용자 지정 모듈을 지정 하 여 기본 HTTP, HTTPS 및 파일 요청 모듈을 재정의할 수 있습니다.  
  
```  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## 참고 항목  
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)   
 [네트워크 설정 스키마](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<system.Net\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)