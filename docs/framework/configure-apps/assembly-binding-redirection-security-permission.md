---
title: "어셈블리 바인딩 리디렉션 보안 권한 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 바인딩 리디렉션"
  - "side-by-side 실행, 어셈블리 바인딩 리디렉션"
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 어셈블리 바인딩 리디렉션 보안 권한
응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.  이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.  이 권한은 [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) 플래그를 설정함으로서 부여됩니다. 이 플래그는 [SecurityPermission Class](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic)에 있습니다.  관리되는 어셈블리에는 기본적으로 권한이 없습니다.  
  
 신뢰할 수 있는 영역\(로컬 컴퓨터\)과 인트라넷 영역에서 실행되는 응용 프로그램에 보안 권한이 부여됩니다.  인터넷 영역에서 실행되는 응용 프로그램은 어셈블리 바인딩 리디렉션을 수행할 수 없게 엄격히 금지됩니다.  
  
 구성 요소 게시자가 제어하는 게시자 정책 파일이나 관리자가 제어하는 컴퓨터 구성 파일에서 어셈블리 리디렉션이 수행될 경우에는 권한이 필요하지 않습니다.  그러나 응용 프로그램 구성 파일의 [\<publisherPolicy apply\="no"\/\>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 요소를 사용하여 응용 프로그램이 게시자 정책을 명시적으로 무시하게 하려면 이 권한이 필요합니다.  
  
 다음 표에서는 **BindingRedirects** 플래그에 대한 기본 보안 설정을 보여 줍니다.  
  
|영역|BindingRedirects 플래그 설정|  
|--------|-----------------------------|  
|신뢰할 수 있는 영역\(로컬 컴퓨터\)|**ON**|  
|인트라넷 영역|**ON**|  
|인터넷 영역|**OFF**|  
|신뢰할 수 없는 영역|**OFF**|  
  
 관리자는 이러한 보안 설정을 변경하여 지정된 컴퓨터의 특정 시나리오를 지원하거나 제한할 수 있습니다.  **BindingRedirects** 플래그 설정을 기본값에서 다른 값으로 변경하기 위한 도구는 없습니다. 따라서 관리자는 사용자 컴퓨터에서 Security.config 파일을 수동으로 편집해야 합니다.  
  
## 참고 항목  
 [Publisher Policy Files and Side\-by\-Side Execution](http://msdn.microsoft.com/ko-kr/97a042be-4d72-40c3-91c0-76fd36bdf133)   
 [방법: 자동 바인딩 리디렉션 사용 설정 및 해제](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)   
 [Side\-by\-Side 실행](../../../docs/framework/deployment/side-by-side-execution.md)