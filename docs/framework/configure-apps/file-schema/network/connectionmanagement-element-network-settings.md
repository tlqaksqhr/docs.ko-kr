---
title: "&lt;connectionManagement&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement> 요소"
  - "connectionManagement 요소"
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;connectionManagement&gt; 요소(네트워크 설정)
네트워크 호스트에 대한 최대 연결 수를 지정합니다.  
  
## 구문  
  
```  
  
      <connectionManagement>   
</connectionManagement>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[추가](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|연결 관리 목록에 IP 주소나 DNS 이름을 추가합니다.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|연결 관리 목록을 지웁니다.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|연결 관리 목록에서 IP 주소나 DNS 이름을 제거합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## 설명  
 `connectionManagement` 요소는 서버나 서버 그룹에 대한 최대 연결 수를 정의합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 서버 www.contoso.com에는 네 개의 연결을 사용하고 다른 모든 서버에는 두 개의 연결을 사용하도록 응용 프로그램을 구성합니다.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.ServicePoint>   
 <xref:System.Net.ServicePointManager>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)