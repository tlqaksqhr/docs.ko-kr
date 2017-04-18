---
title: "웹 설정 스키마 | Microsoft Docs"
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
  - "ASP.NET 구성 시스템, 웹 설정 스키마"
  - "구성 파일[ASP.NET]"
  - "구성 스키마[.NET Framework], 웹 설정"
  - "스키마 웹 설정"
  - "웹 설정, 스키마[ASP.NET]"
  - "Web.config 구성 파일[ASP.NET]"
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 웹 설정 스키마
웹 설정은 ASP.NET 호스팅 계층에서 관리하는 프로세스 전체의 동작에 적용되는 CPU 및 실행 수준 ASP.NET 설정을 지정합니다.  이러한 설정은 ASP.NET 응용 프로그램의 Web.config 파일에 지정되는 응용 프로그램 도메인 형식 설정과 다릅니다.  
  
 웹 설정은 각 .NET Framework 버전의 폴더에 있는 Aspnet.config 파일에 들어 있습니다.  예를 들어, [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]의 Aspnet.config 파일은 다음 폴더에 있습니다.  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 웹 설정은 machine.config, root Web.config, application\-level Web.config 등의 다른 구성 파일에서는 사용되지 않습니다.  
  
 [\<configuration\> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web\> 요소\(웹 설정\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool\> 요소\(웹 설정\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|요소|설명|  
|--------|--------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|ASP.NET 호스팅 계층에서 사용하는 정보를 포함합니다.|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|ASP.NET 호스팅 계층에서 관리하는 프로세스 전체의 동작에 적용되는 CPU 및 실행 수준 ASP.NET 설정을 지정합니다.|  
  
## 참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)