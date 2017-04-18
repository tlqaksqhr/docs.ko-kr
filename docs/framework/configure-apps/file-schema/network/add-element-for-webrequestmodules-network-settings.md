---
title: "webRequestModules의 &lt;add&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> 요소, webRequestModules"
  - "<webRequestModules>, add 요소"
  - "add 요소, webRequestModules"
  - "webRequestModules, add 요소"
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# webRequestModules의 &lt;add&gt; 요소(네트워크 설정)
응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.  
  
## 구문  
  
```  
  
      <add   
  prefix = "URI prefix"   
  type = "module name, Version, Culture, PublicKeyToken"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`prefix`|이 웹 요청 모듈에 의해 처리된 요청의 URI 접두사입니다.|  
|`type`|이 웹 요청 모듈을 구현하는 모듈의 어셈블리 및 클래스 이름입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
## 설명  
 `prefix` 특성은 지정된 웹 요청 모듈을 사용하는 URI 접두사를 정의합니다.  웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜 처리를 위해 등록되지만 서버 상의 경로나 특정 서버로의 요청을 처리하기 위해서 등록될 수도 있습니다.  
  
 웹 요청 모듈은 접두사와 일치하는 URI가 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 메서드에 전달될 때 만들어집니다.  
  
 `prefix` 특성 값은 유효한 URL의 선행 문자\(예: "http" 또는 "http:\/\/www.contoso.com"\)여야 합니다.  
  
 `type` 특성 값은 쉼표로 구분된 유효한 DLL 이름과 해당 클래스 이름이어야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 HTTP에 대한 사용자 지정 웹 요청 모듈을 등록합니다.  Version 및 PublicKeyToken 값을 지정된 모듈에 적합한 값으로 바꾸어야 합니다.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.WebRequest>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)