---
title: "&lt;settings&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#settings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<settings> 요소"
  - "settings 요소"
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;settings&gt; 요소(네트워크 설정)
<xref:System.Net?displayProperty=fullName> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.  
  
## 구문  
  
```  
  
      <settings>  
..<httpListener> … </httpListener>  
..<httpWebRequest> … </httpWebRequest>  
..<ipv6> … </ipv6>  
..<performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
..<socket> … </socket>  
..<webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<xref:System.Net.HttpListener> 클래스에서 사용하는 매개 변수를 사용자 지정합니다.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|웹 요청 매개 변수를 사용자 지정합니다.|  
|[ipv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|IPv6\(인터넷 프로토콜 버전 6\) 지원을 설정합니다.|  
|[\<performanceCounter\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|네트워크 성능 카운터를 설정합니다.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|네트워크 리소스에 대한 연결을 구성합니다.|  
|[소켓](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|소켓 작업에 완료 포트가 사용될지 여부를 지정합니다.|  
|[\<webProxyScript\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|웹 프록시를 검색하는 데 사용되는 스크립트의 특성을 구성합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## 설명  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Net?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)