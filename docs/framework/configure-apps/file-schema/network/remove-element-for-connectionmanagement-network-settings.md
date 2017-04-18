---
title: "connectionManagement의 &lt;remove&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement>, remove 요소"
  - "<remove> 요소, connectionManagement"
  - "connectionManagement, remove 요소"
  - "remove 요소, connectionManagement"
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# connectionManagement의 &lt;remove&gt; 요소(네트워크 설정)
연결 관리 목록에서 IP 주소나 DNS 이름을 제거합니다.  
  
## 구문  
  
```  
  
      <remove   
   name = "server name or IP address"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`address`|IP 주소나 DNS 이름입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|네트워크 호스트에 대한 최대 연결 수를 지정합니다.|  
  
## 설명  
 `remove` 요소는 지정된 서버에 대한 연결 관리 목록 항목을 제거합니다.  
  
 `address` 특성 값은 유효한 IP 주소나 호스트 이름이어야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 서버 www.adventure\-works.com에 대한 연결 관리 목록 항목을 모두 제거한 다음 서버 www.contoso.com에는 네 개의 연결을 사용하고 다른 모든 서버에는 두 개의 연결을 사용하도록 응용 프로그램을 구성합니다.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address = "http://www.adventure-works.com"/>  
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