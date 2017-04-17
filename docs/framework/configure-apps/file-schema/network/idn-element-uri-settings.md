---
title: "&lt;idn&gt; 요소(Uri 설정) | Microsoft Docs"
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
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;idn&gt; 요소(Uri 설정)
IDN\(Internationalized Domain Name\) 구문 분석이 도메인 이름에 적용되는지 여부를 지정합니다.  
  
## 스키마 계층 구조  
 [\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri\> 요소\(Uri 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn\>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## 구문  
  
```  
<idn  
  enabled="All|AllExceptIntranet|None"  
/idn>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**요소**|**설명**|  
|------------|------------|  
|`enabled`|IDN\(Internationalized Domain Name\) 구문 분석이 도메인 이름에 적용되는지 여부를 지정합니다. 기본값은 none입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|URI\(Uniform Resource Identifier\)를 사용하여 표현된 웹 주소를 .NET Framework에서 처리하는 방법을 지정하는 설정을 포함합니다.|  
  
## 설명  
 .NET Framework 3.5, 3.0 SP1 및 2.0 SP1의 기존 <xref:System.Uri> 클래스는 IRI\(International Resource Identifiers\) 및 IDN\(Internationalized Domain Names\)을 지원하도록 확장되었습니다.  IRI 및 IDN 지원을 사용하도록 명확하게 설정하지 않을 경우 .NET Framework 2.0 동작의 어떠한 변경도 현재 사용자에게 표시되지 않습니다.  이를 통해 .NET Framework의 이전 버전과의 응용 프로그램 호환성을 유지할 수 있습니다.  
  
 IRI 지원을 사용하도록 설정하려면 다음과 같은 두 가지 변경이 필요합니다.  
  
1.  .NET Framework 2.0 디렉터리의 machine.config 파일에 다음 줄을 추가합니다.  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  IDN\(Internationalized Domain Name\) 구문 분석을 도메인 이름에 적용할지 여부와 IRI 구문 분석 규칙을 적용해야 하는지 여부를 지정합니다.  machine.config 또는 app.config 파일에서 이 작업을 수행할 수 있습니다.  
  
 사용되는 DNS 서버에 따라 IDN에 대한 세 가지 값이 가능합니다.  
  
-   idn enabled \= All  
  
     이 값은 모든 유니코드 도메인 이름을 해당하는 Punycode 항목\(IDN 이름\)으로 변환합니다.  
  
-   idn enabled \= AllExceptIntranet  
  
     이 값은 해당하는 Punycode 항목\(IDN 이름\)을 사용하도록 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환합니다.  이 경우 로컬 인트라넷에 있는 국가별 이름을 처리하기 위해 인트라넷에 사용되는 DNS 서버가 유니코드 이름 확인을 지원해야 합니다.  
  
-   idn enabled \= None  
  
     이 값은 Punycode를 사용하도록 어떠한 유니코드 도메인 이름도 변환하지 않습니다.  이 값은 .NET Framework 2.0 동작과 일치하는 기본값입니다.  
  
 IDN을 사용하도록 설정하면 도메인 이름의 모든 유니코드 레이블은 동등한 Punycode 항목으로 변환됩니다.  Punycode 이름은 ASCII 문자만 포함하고 항상 xn\-\- 접두사로 시작합니다.  이는 대부분의 DNS 서버가 ASCII 문자만 지원하므로\(RFC 3940 참조\) 인터넷에서 기존 DNS 서버를 지원하기 위해서입니다.  
  
### 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
  
### 설명  
 다음 코드 예제에서는 IRI 구문 분석 및 IDN 이름을 지원하기 위해 <xref:System.Uri> 클래스에 사용되는 구성을 보여 줍니다.  
  
### 코드  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)