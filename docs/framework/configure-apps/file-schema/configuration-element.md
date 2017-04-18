---
title: "&lt;configuration&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<configuration> 요소"
  - "configuration 요소"
  - "컨테이너 태그, <configuration> 요소"
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;configuration&gt; 요소
공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.  
  
 **\<적용\>**  
  
## 구문  
  
```  
  
      <configuration>   
   <!-- configuration settings -->   
</configuration>  
```  
  
## 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<assemblyBinding\> 요소](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|구성 수준에서 어셈블리 바인딩 정책을 지정합니다.|  
|[시작 설정 스키마](../../../../docs/framework/configure-apps/file-schema/startup/index.md)|시작 설정 스키마의 모든 요소입니다.|  
|[런타임 설정 스키마](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)|런타임 설정 스키마의 모든 요소입니다.|  
|[원격 설정 스키마](http://msdn.microsoft.com/ko-kr/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)|원격 설정 스키마의 모든 요소입니다.|  
|[네트워크 설정 스키마](../../../../docs/framework/configure-apps/file-schema/network/index.md)|네트워크 설정 스키마의 모든 요소입니다.|  
|[암호화 설정 스키마](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)|암호화 설정 스키마의 모든 요소입니다.|  
|[구성 섹션 스키마](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)|구성 섹션 설정 스키마의 모든 요소입니다.|  
|[추적 및 디버그 설정 스키마](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)|추적 및 디버그 설정 스키마의 모든 요소입니다.|  
|[ASP.NET 설정 스키마](http://msdn.microsoft.com/ko-kr/116608f3-c03d-4413-9fc7-978703e18b0f)|ASP.NET 웹 사이트 및 응용 프로그램 구성을 위한 요소를 비롯한 ASP.NET 구성 스키마의 모든 요소입니다.  Web.config 파일에서 사용됩니다.|  
|[XML Web Services 설정 스키마](http://msdn.microsoft.com/ko-kr/f84d6d55-1add-4eb7-ae46-33df5833ea2e)|Web services 설정 스키마의 모든 요소입니다.|  
|[웹 설정 스키마](../../../../docs/framework/configure-apps/file-schema/web/index.md)|ASP.NET이 IIS와 같은 호스트 응용 프로그램과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다.  aspnet.config 파일에서 사용됩니다.|  
  
## 설명  
 각 구성 파일에는 **\<configuration\>** 요소를 하나만 사용할 수 있습니다.  
  
## 참고 항목  
 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)