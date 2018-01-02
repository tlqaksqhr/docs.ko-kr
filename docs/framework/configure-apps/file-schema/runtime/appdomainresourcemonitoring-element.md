---
title: "&lt;appDomainResourceMonitoring&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58caa7458d96ca7bb9088b607a83b2d6be667cae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainresourcemonitoringgt-element"></a>&lt;appDomainResourceMonitoring&gt; 요소
프로세스의 수명 동안 프로세스의 모든 응용 프로그램 도메인에서 통계를 수집하도록 런타임에 명령합니다.  
  
 \<configuration>  
\<런타임 >  
\<appDomainResourceMonitoring >  
  
## <a name="syntax"></a>구문  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에 응용 프로그램 도메인 리소스 모니터링에 대 한 통계를 수집 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.|  
|`false`|응용 프로그램 도메인 리소스 모니터링에 대 한 통계 수집 되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 도메인 리소스 모니터링은 호스트 하는 관리 되는 응용 프로그램 도메인 클래스를 통해 사용할 수 있는 [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 이벤트 추적에 대 한 ETW (Windows). 모니터링이 사용 하는 경우 프로세스의 수명에 대 한 프로세스의 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.  
  
 관리 코드에서 모니터링을 사용 하려면 사용 하 여는 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성입니다.  
  
 이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상.  
  
## <a name="example"></a>예  
 다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
