---
title: "&lt;module&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#module"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<module> 요소"
  - "module 요소"
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;module&gt; 요소(네트워크 설정)
응용 프로그램에 새 프록시 모듈을 추가합니다.  
  
## 구문  
  
```  
  
      <module   
   type = "name", System, Version="version number", Culture="culture", PublicKeyToken="token" "   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`type`|프록시를 구현하는 모듈의 이름 및 사양입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP\(Hypertext Transfer Protocol\) 프록시 서버를 구성합니다.|  
  
## 설명  
 `module` 요소는 <xref:System.Net.IWebProxy> 인터페이스를 구현하는 프록시 클래스를 등록하며  프록시 클래스를 등록한 다음에는, `module` 을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.  
  
 `type` 특성 값은 유효한 DLL\(동적 연결 라이브러리\)의 이름 및 모듈의 클래스 이름이어야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 사용자 지정 프록시 클래스를 등록합니다.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type = "Test.CustomWebProxy, System, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.IWebProxy?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)