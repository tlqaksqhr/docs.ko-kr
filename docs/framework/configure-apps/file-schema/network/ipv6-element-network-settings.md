---
title: "&lt;ipv6&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<ipv6> 요소"
  - "ipv6 요소"
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;ipv6&gt; 요소(네트워크 설정)
<xref:System.Net.Dns> 클래스의 사용되지 않는 멤버로부터의 IPv6\(인터넷 프로토콜 버전 6\) 응답을 사용 가능하게 설정합니다.  
  
## 구문  
  
```  
  
      <ipv6  
  enabled="true|false"  
/ipv6>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`enabled`|<xref:System.Net.Dns> 클래스의 멤버가 IPv6\(인터넷 프로토콜 버전 6\) 주소를 반환할지 여부를 지정합니다.  기본값은 `false`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
 이 설정은 <xref:System.Net.Dns> 클래스의 사용되지 않는 멤버인 <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A> 및 <xref:System.Net.Dns.Resolve%2A>에 대한 IPv6 지원을 사용 가능하게 설정합니다.  <xref:System.Net?displayProperty=fullName> 네임스페이스의 다른 멤버의 경우 운영 체제에서 IPv6이 설정되면 IPv6 주소가 반환될 수 있습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Net.Dns> 클래스에 대한 IPv6 지원을 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Dns?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)