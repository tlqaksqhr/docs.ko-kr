---
title: "시작 설정 스키마 | Microsoft Docs"
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
helpviewer_keywords: 
  - "구성 스키마[.NET Framework], 시작 설정"
  - "스키마 시작 설정"
  - "시작 설정 스키마"
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 시작 설정 스키마
시작 설정은 응용 프로그램을 실행할 공용 언어 런타임 버전을 지정합니다.  
  
|요소|설명|  
|--------|--------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|응용 프로그램이 공용 언어 런타임 버전 1.0만 지원하도록 지정합니다.  런타임 버전 1.1로 작성된 응용 프로그램은 **\<supportedRuntime\>** 요소를 사용해야 합니다.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.|  
|[\<시작\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|**\<requiredRuntime\>** 및 **\<supportedRuntime\>** 요소를 포함합니다.|  
  
## 참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ko-kr/c376208d-980d-42b4-865b-fbe0d9cc97c2)