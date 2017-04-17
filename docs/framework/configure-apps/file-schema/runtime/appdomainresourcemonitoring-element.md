---
title: "&lt;appDomainResourceMonitoring&gt; 요소 | Microsoft Docs"
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
  - "<appDomainResourceMonitoring> 요소"
  - "appDomainResourceMonitoring 요소"
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;appDomainResourceMonitoring&gt; 요소
프로세스의 수명 동안 프로세스의 모든 응용 프로그램 도메인에 대한 통계를 수집하도록 런타임에 지시합니다.  
  
## 구문  
  
```  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 응용 프로그램 도메인 리소스 모니터링에 대한 통계를 수집하는지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`true`|응용 프로그램 도메인 리소스 모니터링에 대한 통계가 수집됩니다.|  
|`false`|응용 프로그램 도메인 리소스 모니터링에 대한 통계가 수집되지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 응용 프로그램 도메인 리소스 모니터링은 관리되는 응용 프로그램 도메인 클래스, 호스팅 [ICLRAppDomainResourceMonitor](../../../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 ETW\(Windows용 이벤트 추적\)를 통해 사용할 수 있습니다.  모니터링이 설정되어 있으면 프로세스 수명 동안 프로세스의 모든 응용 프로그램 도메인에 대한 통계가 수집됩니다.  
  
 관리 코드에서 모니터링을 사용하도록 설정하려면 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성을 사용합니다.  
  
 이 구성 요소는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용하도록 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)