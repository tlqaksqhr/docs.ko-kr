---
title: "&lt;webRequestModules&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<webRequestModules> 요소"
  - "webRequestModules 요소"
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;webRequestModules&gt; 요소(네트워크 설정)
네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.  
  
## 구문  
  
```  
  
      <webRequestModules>   
</webRequestModules>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[추가](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 등록된 모든 웹 요청 모듈을 제거합니다.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.|  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## 설명  
 `webRequestModules` 요소는 네트워크 호스트로 정보 요청을 처리하기 위해 <xref:System.Net.WebRequest> 클래스의 하위 항목을 등록합니다.  웹 요청 모듈은 <xref:System.Net.IWebRequestCreate> 인터페이스를 구현해야 합니다.  
  
 .NET Framework에는 http:\/\/, https:\/\/ 및 file:\/\/로 시작하는 URI에 대한 웹 요청 모듈이 들어 있습니다.  구성 파일에 사용자 지정 모듈을 등록해야만 기본 모듈을 재정의할 수 있습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 기본 HTTP 모듈을 등록합니다.  Version 및 PublicKeyToken 값을 지정된 모듈에 적합한 값으로 바꾸어야 합니다.  
  
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
 <xref:System.Net.IWebRequestCreate>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)