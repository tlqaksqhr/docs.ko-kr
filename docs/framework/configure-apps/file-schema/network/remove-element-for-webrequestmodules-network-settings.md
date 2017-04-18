---
title: "webRequestModules의 &lt;remove&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> 요소, webRequestModules"
  - "<webRequestModules>, remove 요소"
  - "remove 요소, webRequestModules"
  - "webRequestModules, remove 요소"
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# webRequestModules의 &lt;remove&gt; 요소(네트워크 설정)
응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.  
  
## 구문  
  
```  
  
      <remove   
  name = "URI prefix"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`name`|이 웹 요청 모듈에 의해 처리된 요청의 URI 접두사입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
## 설명  
 `remove` 요소는 지정된 URI 접두사에 대해 등록된 웹 요청 모듈을 제거합니다.  
  
 `prefix` 특성 값은 "http" 또는 "http:\/\/www.contoso.com"과 같은 올바른 URI의 선행 문자여야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 HTTP에 대한 기존 웹 요청 모듈을 제거한 다음 www.contoso.com에 대한 HTTP 요청의 새로운 사용자 지정 웹 요청 모듈을 등록합니다.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix = "http">  
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