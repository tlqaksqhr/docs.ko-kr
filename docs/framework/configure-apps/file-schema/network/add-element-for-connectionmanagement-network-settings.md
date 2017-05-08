---
title: "connectionManagement의 &lt;add&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> 요소, connectionManagement"
  - "<connectionManagement>, add 요소"
  - "add 요소, connectionManagement"
  - "connectionManagement, add 요소"
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# connectionManagement의 &lt;add&gt; 요소(네트워크 설정)
연결 관리 목록에 IP 주소 또는 DNS 이름을 추가합니다.  
  
## 구문  
  
```  
  
        <add   
   address = "address expression"   
   maxconnection = integer   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`address`|IP 주소 또는 DNS 이름을 설명하는 문자열입니다.|  
|`maxconnection`|서버에 허용되는 최대 연결 수입니다.  제공되지 않은 경우 기본값은 2입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|네트워크 호스트에 대한 최대 연결 수를 지정합니다.|  
  
## 설명  
 `address` 특성의 값은 모든 연결을 나타내는 별표 또는 `<schema>://<idn_hostname>[:<port>]` 형식의 문자열이어야 합니다.  
  
 HTTP API에 전달된 URI가 유니코드를 포함하는 경우 punicode 문자열을 반환할 수 있는 <xref:System.Uri.DnsSafeHost%2A>를 통해 이름이 내부적으로 변환됩니다\(현재 IDN 구성에 따라 동작이 달라짐\).  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일\(Machine.config\)에서 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 www.contoso.com 서버에 대한 연결 4개와 다른 모든 서버에 대한 연결 2개를 사용하도록 응용 프로그램을 구성합니다.  
  
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