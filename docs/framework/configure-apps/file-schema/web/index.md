---
title: "웹 설정 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: a4ece61330fe8e41d9afb894791f9f9e36db35f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="web-settings-schema"></a>웹 설정 스키마
웹 설정은 CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다. 이러한 설정은 ASP.NET 응용 프로그램의 Web.config 파일에서 지정된 응용 프로그램 도메인 유형 설정과 다릅니다.  
  
 웹 설정은 .NET Framework의 버전 설치 폴더에 위치한 Aspnet.config 파일에 포함됩니다. 예를 들어 [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]에 대한 Aspnet.config 파일은 다음 폴더에 위치합니다.  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 웹 설정은 machine.config 파일, 루트 Web.config 또는 응용 프로그램 수준 Web.config 파일과 같은 다른 구성 파일에는 사용되지 않습니다.  
  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web> 요소(웹 설정)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool> 요소(웹 설정)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|ASP.NET 호스팅 계층에서 사용하는 정보가 포함됩니다.|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
