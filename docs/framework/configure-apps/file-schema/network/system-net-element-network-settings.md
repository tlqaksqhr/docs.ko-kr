---
title: "&lt;system.Net&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.Net> 요소"
  - "system.Net 요소"
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;system.Net&gt; 요소(네트워크 설정)
.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.  
  
## 구문  
  
```  
  
      <system.net>   
</system.net>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|인터넷 요청을 인증하는 데 사용되는 모듈을 지정합니다.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|인터넷 호스트에 대한 최대 연결 수를 지정합니다.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP\(Hypertext Transfer Protocol\) 프록시 서버를 구성합니다.|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|SMTP\(Simple Mail Transport Protocol\) 메일 보내기 옵션을 구성합니다.|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 및 관련 자식 네임스페이스에서 클래스의 기본 네트워크 옵션을 구성합니다.|  
|[\<webRequestModules\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|인터넷 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[적용](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|모든 네임스페이스에 대한 설정을 포함합니다.|  
  
## 설명  
 [\<system.net\>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 요소는 <xref:System.Net> 및 자식 네임스페이스의 클래스에 대한 설정을 포함합니다.  이 설정은 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 호스트에서 정보를 받는 데 사용되는 인터넷 요청 모듈을 구성합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Net> 클래스에서 사용되는 일반적인 구성을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type = "System.Net.DigestClient" />  
      <add type = "System.Net.NegotiateClient" />  
      <add type = "System.Net.KerberosClient" />  
      <add type = "System.Net.NtlmClient" />  
      <add type = "System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault = "true"  
        bypassonlocal = "true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix = "http"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "https"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "file"  
        type = "System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)