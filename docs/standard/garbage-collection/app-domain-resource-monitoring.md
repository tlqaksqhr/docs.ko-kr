---
title: "응용 프로그램 도메인 리소스 모니터링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>응용 프로그램 도메인 리소스 모니터링
응용 프로그램 도메인 리소스 모니터링 (ARM)에 호스트를 응용 프로그램 도메인 별로 CPU 및 메모리 사용량을 모니터링할 수 있습니다. ASP.NET 같은 장기 실행 프로세스의 많은 응용 프로그램 도메인을 사용 하는 호스트에 대 한 유용 합니다. 호스트는 문제가 있는 응용 프로그램을 식별할 수 있으 나만 전체 프로세스의 성능이 저하 되는지 하는 응용 프로그램의 응용 프로그램 도메인을 언로드할 수 있습니다. ARM 이러한 결정을 내리는 데 사용할 수 있는 정보를 제공 합니다.  
  
 예를 들어 호스팅 서비스가 ASP.NET 서버에서 실행 되는 많은 응용 프로그램을 포함할 수 있습니다. 한 응용 프로그램 프로세스에서 너무 많은 메모리 또는 프로세서 시간이 너무 오래 사용을 시작 하면 호스팅 서비스에서 문제가 발생 하는 응용 프로그램 도메인을 식별 하기 ARM를 사용할 수 있습니다.  
  
 ARM은가 볍 라이브 응용 프로그램에서 사용 하도록 합니다. ETW (Windows 용) 또는 직접 관리 또는 네이티브 Api를 통해 이벤트 추적을 사용 하 여 정보에 액세스할 수 있습니다.  
  
## <a name="enabling-resource-monitoring"></a>리소스 모니터링을 사용 하도록 설정  
 ARM 네 가지 방법으로 사용할 수 있는: 공용 언어 런타임 (CLR)이 시작 될 때 구성 파일을를 제공 하 여 관리 되지 않는 사용 하 여 호스팅 API 관리 코드를 사용 하거나 ARM ETW 이벤트를 수신 합니다.  
  
 ARM이 활성화 되는 즉시 프로세스의 모든 응용 프로그램 도메인에서 데이터 수집 시작 합니다. ARM을 활성화 하기 전 응용 프로그램 도메인이 만들어진 경우 ARM 활성화 응용 프로그램 도메인이 만들어진 때가 아니라 누적 데이터 시작 됩니다. 활성화 되 면 ARM은 해제할 수 없습니다.  
  
-   추가 하 여 ARM CLR 시작에 사용할 수 있습니다는 [ \<appDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) 구성 파일을 설정 하는 요소는 `enabled` 특성을 `true`합니다. 값이 `false` ARM 시작 시 사용할 수 없습니다 (기본값)만 의미 이므로, 다른 인증 메커니즘 중 하나를 사용 하 여 나중에 활성화할 수 있습니다.  
  
-   호스트를 요청 하 여 ARM을 활성화할 수는 [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스를 호스트 합니다. 이 인터페이스 성공적으로 가져온 후에 ARM 활성화 됩니다.  
  
-   관리 코드는 정적 설정 하 여 ARM를 사용할 수 있습니다 (`Shared` Visual basic에서) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> 속성을 `true`합니다. 속성이 설정 되는 즉시 ARM 활성화 됩니다.  
  
-   ETW 이벤트를 수신 하 여 시작 된 후 ARM을 사용할 수 있습니다. ARM을 사용 하 고 공용 공급자를 사용 하도록 설정 하면 모든 응용 프로그램 도메인에 대 한 이벤트를 발생 시키기 시작 `Microsoft-Windows-DotNETRuntime` 를 사용 하 여는 `AppDomainResourceManagementKeyword` 키워드입니다. 데이터와 응용 프로그램 도메인과 스레드 상관 관계를 분석 하려면 설정도 해야는 `Microsoft-Windows-DotNETRuntimeRundown` 인 공급자는 `ThreadingKeyword` 키워드입니다.  
  
## <a name="using-arm"></a>ARM를 사용 하 여  
 ARM에서는 세 가지 종류의 메모리 사용에 대 한 정보 및 응용 프로그램 도메인에서 사용 되는 총 프로세서 시간을 제공 합니다.  
  
-   **응용 프로그램 도메인에 대 한 프로세서 시간 (초) 총**: 시간의 수명 동안 응용 프로그램 도메인에서 실행 하는 데 걸린 모든 스레드에 대 한 운영 체제에서 보고 한 스레드 시간을 추가 하 여이 계산 됩니다. 차단 되거나 대기 중인 스레드 프로세서 시간을 사용 하지 않습니다. 스레드가 네이티브 코드를 호출 스레드가 네이티브 코드에서 소비한 시간 생성 되었으므로 호출 응용 프로그램 도메인에 대 한 수에 포함 됩니다.  
  
    -   관리 되는 API: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 속성입니다.  
  
    -   API 호스팅: [iclrappdomainresourcemonitor:: Getcurrentcputime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md) 메서드.  
  
    -   ETW 이벤트: `ThreadCreated`, `ThreadAppDomainEnter`, 및 `ThreadTerminated` 이벤트입니다. 공급자 및 키워드에 대 한 내용은 "AppDomain 리소스 모니터링 이벤트"를 참조 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)합니다.  
  
-   **바이트에서의 수명 동안 응용 프로그램 도메인으로 만든 관리 되는 할당 총**: 할당 된 개체의 수명이 짧은 수 있으므로 총 할당 항상 응용 프로그램 도메인의 메모리 사용을 반영 하지는 않습니다. 그러나 할당 하 고 큰 수의 개체를 해제 하는 응용 프로그램, 경우에 할당의 비용 상당한 수 있습니다.  
  
    -   관리 되는 API: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
    -   API 호스팅: [iclrappdomainresourcemonitor:: Getcurrentallocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md) 메서드.  
  
    -   ETW 이벤트: `AppDomainMemAllocated` 이벤트 `Allocated` 필드입니다.  
  
-   **관리 되는 메모리를 바이트 단위로 응용 프로그램 도메인에서 참조 하는 가장 최근의 전체 차단 수집에도 유지 되 고**:이 번호는 정확한 full, 한 후에 차단 수집 합니다. (즉 백그라운드에서 발생 하 고 응용 프로그램을 차단 하지 않습니다는 동시 컬렉션입니다.) 예를 들어는 <xref:System.GC.Collect?displayProperty=nameWithType> 메서드 오버 로드 하면 전체 차단 수집 합니다.  
  
    -   관리 되는 API: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
    -   API 호스팅: [iclrappdomainresourcemonitor:: Getcurrentsurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) 메서드, `pAppDomainBytesSurvived` 매개 변수입니다.  
  
    -   ETW 이벤트: `AppDomainMemSurvived` 이벤트 `Survived` 필드입니다.  
  
-   **관리 되는 메모리 (바이트), 프로세스에 의해 참조 되는 및 가장 최근의 전체 차단 수집에도 유지 되는 총**: 개별 응용 프로그램 도메인에 대 한 남은 메모리는이 수와 비교할 수 있습니다.  
  
    -   관리 되는 API: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
    -   API 호스팅: [iclrappdomainresourcemonitor:: Getcurrentsurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) 메서드, `pTotalBytesSurvived` 매개 변수입니다.  
  
    -   ETW 이벤트: `AppDomainMemSurvived` 이벤트 `ProcessSurvived` 필드입니다.  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>전체 시기를 결정 하는, 차단 수집이 발생 합니다.  
 남은 메모리의 수를 정확 하 게 하는 시기를 확인 하려면 전체 차단 수집 발생 했을 때만 알고 있어야 합니다. 이 작업을 수행 하는 방법은 ARM 통계를 검사 하는 데 API에 따라 달라 집니다.  
  
#### <a name="managed-api"></a>관리 되는 API  
 속성을 사용 하는 경우는 <xref:System.AppDomain> 사용할 수 있습니다 클래스는 <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> 전체 컬렉션에 대 한 알림을 등록 합니다. 컬렉션의 접근 방식 보다는 컬렉션의 완료를 대기 하는 사용 하는 임계값 중요 하지 않습니다. 호출할 수 있습니다는 <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> 메서드를 전체 수집이 완료 될 때까지 차단 합니다. 루프에서 메서드를 호출 하 고 메서드가 반환 될 때마다 필요한 분석을 수행 하는 스레드를 만들 수 있습니다.  
  
 호출할 수 있습니다는 <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> 메서드 주기적으로 보려는 경우에 2 세대 컬렉션 개수 증가 했습니다. 폴링 빈도 따라이 기술을 제공 하지 않는 있습니다을 정확한 것으로 전체 컬렉션의 항목을 나타냅니다.  
  
#### <a name="hosting-api"></a>호스팅 API  
 관리 되지 않는 호스팅 API를 사용 하는 경우 호스트에 전달 해야 CLR 구현의 [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) 인터페이스입니다. CLR에서는 [ihostgcmanager:: Suspensionending](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) 수집이 발생 하는 동안 일시 중단 된 스레드의 실행 될 때 메서드. CLR은 호스트 전체 또는 부분 컬렉션 했는지 여부를 결정할 수 있도록는 메서드의 매개 변수로 완료 된 컬렉션의 생성을 전달 합니다. 구현에서 [ihostgcmanager:: Suspensionending](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) 메서드 업데이트 되는 즉시 개수 검색 되도록 하려면 유지 된 메모리를 쿼리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor 인터페이스](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)
