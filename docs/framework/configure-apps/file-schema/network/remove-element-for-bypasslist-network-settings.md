---
title: "bypasslist의 &lt;remove&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>, remove 요소"
  - "bypasslist, remove 요소"
  - "remove 요소, bypasslist"
  - "remove 요소, bypasslist"
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# bypasslist의 &lt;remove&gt; 요소(네트워크 설정)
프록시 비사용 목록에서 IP 주소나 DNS 이름을 제거합니다.  
  
## 구문  
  
```  
  
      <remove   
   name = "regular expression"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`name`|IP 주소나 DNS 이름을 나타내는 정규식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.|  
  
## 설명  
 `remove` 요소는 프록시 서버를 사용하지 않는 주소 목록에서 IP 주소나 DNS 서버 이름을 나타내는 정규식을 제거합니다.  이 주소는 구성 파일 앞이나 구성 계층 구조의 상위 수준에서 정의됩니다.  
  
 `name` 특성의 값은 IP 주소나 호스트 이름의 집합을 나타내는 정규식이어야 합니다.  
  
 정규식에 대한 자세한 내용은 [.NET Framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)을 참조하십시오.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 adventure\-works.com 도메인에 대한 모든 이전 정의를 제거한 다음 비사용 목록에 contoso.com 도메인을 추가합니다.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove name = "[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)