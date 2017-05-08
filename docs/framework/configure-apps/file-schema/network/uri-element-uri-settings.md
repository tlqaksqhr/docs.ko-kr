---
title: "&lt;Uri&gt; 요소(Uri 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;Uri&gt; 요소(Uri 설정)
URI\(Uniform Resource Identifier\)를 사용하여 표현된 웹 주소를 .NET Framework에서 처리하는 방법을 지정하는 설정을 포함합니다.  
  
## 스키마 계층 구조  
 [\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri\>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## 구문  
  
```  
<uri>  
</uri>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|IDN\(Internationalized Domain Name\) 구문 분석이 도메인 이름에 적용되는 경우 지정합니다.|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|IRI\(International Resource Identifier\) 구문 분석이 <xref:System.Uri>에 적용되는지 여부와 IRI 구문 분석 규칙을 적용해야 하는지 여부를 지정합니다.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|특정 스키마에 대해 <xref:System.Uri>가 구문 분석되는 방식을 지정합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[적용](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|모든 네임스페이스에 대한 설정을 포함합니다.|  
  
## 설명  
 `uri` 요소는 <xref:System.Net> 네임스페이스의 클래스에 사용되는 <xref:System.Uri> 클래스의 멤버에 대한 설정을 포함합니다.  이러한 설정은 IRI 및 IDN 지원을 구성합니다.  
  
## 예제  
  
### 설명  
 다음 코드 예제에서는 IRI 구문 분석 및 IDN 이름을 지원하기 위해 <xref:System.Uri> 클래스에 사용되는 구성을 보여 줍니다.  이 예제에서는 모든 스키마 설정을 지운 다음, http 스키마에서 백분율 기호로 인코딩된 경로 구분 기호를 이스케이프하지 않아도 되도록 지원을 추가합니다.  
  
### 코드  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## 참고 항목  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)