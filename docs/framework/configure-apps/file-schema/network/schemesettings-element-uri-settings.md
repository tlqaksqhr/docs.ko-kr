---
title: "&lt;schemeSettings&gt; 요소(URI 설정) | Microsoft Docs"
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
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;schemeSettings&gt; 요소(URI 설정)
특정 스키마에 대해 <xref:System.Uri>가 구문 분석되는 방식을 지정합니다.  
  
## 구문  
  
```  
  
      <schemeSettings>   
</schemeSettings>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[추가](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|구성표 이름에 대해 구성표 설정을 추가합니다.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|기존의 모든 구성표 설정을 지웁니다.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|구성표 이름에 대한 구성표 설정을 제거합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|URI\(Uniform Resource Identifier\)를 사용하여 표현된 웹 주소를 .NET Framework에서 처리하는 방법을 지정하는 설정을 포함합니다.|  
  
## 설명  
 기본적으로 <xref:System.Uri?displayProperty=fullName> 클래스는 경로 압축을 실행하기 전에 백분율로 인코딩된 경로 구분 기호를 이스케이프 해제합니다.  다음과 같은 공격에 대한 보안 메커니즘으로 구현되었습니다.  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 이 URI가 백분율 인코딩된 문자를 올바르게 처리하지 못하는 모듈을 전달한 경우 서버에서 다음 명령이 실행될 수 있습니다.  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 따라서, <xref:System.Uri?displayProperty=fullName> 클래스가 먼저 경로 구분 기호에서 이스케이프 해제되고 경로 압축을 적용합니다.  위의 악의적인 URL을 <xref:System.Uri?displayProperty=fullName> 클래스 생성자에 전달하면 다음 URI가 됩니다.  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 이 기본 동작은 특정 스키마에 대한 schemeSettings 구성 옵션을 사용하여 이스케이프 해제 백분율로 인코딩된 경로 구분 기호가 아닌 값으로 수정할 수 있습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 http 스키마에서 백분율 기호로 인코딩된 경로 구분 기호를 이스케이프하지 않아도 되도록 지원하는 <xref:System.Uri> 클래스에서 사용하는 구성을 보여줍니다.  
  
```  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## 요소 정보  
  
|||  
|-|-|  
|네임스페이스|시스템|  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있음||  
  
## 참고 항목  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)