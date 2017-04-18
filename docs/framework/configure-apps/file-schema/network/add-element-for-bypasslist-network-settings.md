---
title: "bypasslist의 &lt;add&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> 요소, bypasslist"
  - "<bypasslist>, add 요소"
  - "add 요소, bypasslist"
  - "bypasslist, add 요소"
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# bypasslist의 &lt;add&gt; 요소(네트워크 설정)
프록시 비사용 목록에 IP 주소나 DNS 이름을 추가합니다.  
  
## 구문  
  
```  
  
      <add   
   address = "regular expression"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|**address**|IP 주소나 DNS 이름을 나타내는 정규식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.|  
  
## 설명  
 `add` 요소는 프록시 서버를 사용하지 않는 주소 목록에 IP 주소나 DNS 서버 이름을 나타내는 정규식을 삽입합니다.  
  
 `address` 특성의 값은 IP 주소나 호스트 이름의 집합을 나타내는 정규식이어야 합니다.  
  
 이 요소에 정규식을 지정할 때는 주의해야 합니다.  정규식 "\[a\-z\]\+\\.contoso\\.com"은 contoso.com 도메인에 있는 모든 호스트와 일치할 뿐 아니라 contoso.com.cpandl.com 도메인의 호스트와도 일치합니다.  contoso.com 도메인의 호스트와만 일치시키려면 앵커\("$"\)를 사용합니다\("\[a\-z\]\+\\.contoso\\.com$"\).  
  
 정규식에 대한 자세한 내용은 [.NET Framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)을 참조하십시오.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 비사용 목록에 두 개의 주소를 추가합니다.  첫째 주소는 contoso.com 도메인에 있는 모든 서버에 프록시를 사용하지 않으며 둘째 주소는 IP 주소가 192.168로 시작하는 모든 서버에 프록시를 사용하지 않습니다.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)