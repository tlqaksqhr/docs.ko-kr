---
title: "&lt;proxy&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<proxy> 요소"
  - "proxy 요소"
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;proxy&gt; 요소(네트워크 설정)
프록시 서버를 정의합니다.  
  
## 구문  
  
```  
  
      <proxy   
  autoDetect="true|false|unspecified"    
  bypassonlocal="true|false|unspecified"   
  proxyaddress="uriString"  
  scriptLocation="uriString"   
  usesystemdefault="true|false|unspecified "   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`autoDetect`|프록시를 자동으로 검색할지 여부를 지정합니다.  기본값은 `unspecified`입니다.|  
|`bypassonlocal`|로컬 리소스에 프록시가 사용되지 않는지 여부를 지정합니다.  로컬 리소스로는 로컬 서버\(http:\/\/localhost, http:\/\/loopback 또는 http:\/\/127.0.0.1\)와 마침표가 없는 URI\(http:\/\/webserver\)가 포함됩니다.  기본값은 `unspecified`입니다.|  
|`proxyaddress`|사용할 프록시 URI를 지정합니다.|  
|`scriptLocation`|구성 스크립트의 위치를 지정합니다.|  
|`usesystemdefault`|Internet Explorer 프록시 설정을 사용할지 여부를 지정합니다.  `true`로 설정하면 후속 특성으로 Internet Explorer 프록시 설정이 재정의됩니다.  기본값은 `unspecified`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP\(Hypertext Transfer Protocol\) 프록시 서버를 구성합니다.|  
  
## 텍스트 값  
  
## 설명  
 `proxy` 요소는 응용 프로그램에 대한 프록시 서버를 정의합니다.  이 요소가 구성 파일에 없으면 .NET Framework에서는 Internet Explorer의 프록시 설정을 사용합니다.  
  
 `proxyaddress` 특성 값은 올바른 형식의 URI\(Uniform Resource Indicator\)여야 합니다.  
  
 `scriptLocation` 특성은 프록시 구성 스크립트의 자동 감지를 나타냅니다.  Internet Explorer에서 **자동 구성 스크립트 사용** 옵션을 선택하면 <xref:System.Net.WebProxy> 클래스는 일반적으로 Wpad.dat로 지칭되는 구성 스크립트를 찾으려고 합니다.  
  
 .NET Framework 버전 2.0으로 마이그레이션할 버전 1.1 응용 프로그램에 대해서는 `usesystemdefault` 특성을 사용하십시오.  
  
 `proxyaddress`가 잘못된 기본 프록시를 지정하는 경우 예외가 throw됩니다.  예외의 <xref:System.Exception.InnerException%2A> 속성은 오류의 근본 원인에 대한 자세한 내용을 제공해야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 Internet Explorer 프록시의 기본값을 사용하고 프록시 주소를 지정한 후 로컬 액세스에 대해 해당 프록시를 무시합니다.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)