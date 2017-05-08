---
title: "webRequestModules의 &lt;clear&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> 요소, webRequestModules"
  - "<webRequestModules>, clear 요소"
  - "clear 요소, webRequestModules"
  - "webRequestModules, clear 요소"
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# webRequestModules의 &lt;clear&gt; 요소(네트워크 설정)
응용 프로그램에서 등록된 모든 웹 요청 모듈을 제거합니다.  
  
## 구문  
  
```  
  
<clear/>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
## 설명  
 `clear` 요소는 구성 파일이나 구성 계층 구조의 상위 수준에서 이전에 정의되었던 등록된 웹 요청 모듈을 모두 제거합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 웹 요청 모듈을 모두 지운 다음 HTTP에 대한 웹 요청 모듈을 등록합니다.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
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