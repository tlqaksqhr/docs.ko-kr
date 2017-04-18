---
title: "Application Domain Resource Monitoring | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "monitoring managed memory use by application domain"
  - "application domains, memory use"
  - "memory use, monitoring"
  - "application domains, resource monitoring"
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Application Domain Resource Monitoring
ARM\(응용 프로그램 도메인 리소스 모니터링\)을 사용하면 호스트에서 CPU와 메모리 사용을 응용 프로그램 도메인별로 모니터링할 수 있습니다.  이 기능은 장기 실행 프로세스에서 많은 응용 프로그램 도메인을 사용하는 ASP.NET과 같은 호스트에서 유용합니다.  호스트는 전체 프로세스의 성능에 부정적인 영향을 미치는 응용 프로그램의 응용 프로그램 도메인을 언로드할 수 있지만 이를 위해서는 호스트에서 문제가 있는 응용 프로그램을 식별할 수 있어야 합니다.  ARM은 이러한 판단을 내리는 데 사용할 수 있는 정보를 제공합니다.  
  
 예를 들어 호스팅 서비스의 ASP.NET 서버에 많은 수의 응용 프로그램이 실행 중일 수 있습니다.  프로세스에서 한 응용 프로그램이 메모리를 너무 많이 소비하기 시작하거나 프로세서 시간을 너무 많이 점유하기 시작하면 호스팅 서비스는 ARM을 사용하여 문제를 일으키는 응용 프로그램 도메인을 식별할 수 있습니다.  
  
 ARM은 가볍기 때문에 라이브 응용 프로그램에서 무리 없이 사용할 수 있습니다.  ETW\(Windows용 이벤트 추적\)를 사용하거나 관리되는 API 또는 네이티브 API를 직접 통해 이 정보에 액세스할 수 있습니다.  
  
## 리소스 모니터링 활성화  
 ARM은 네 가지 방법으로 활성화할 수 있습니다. CLR\(공용 언어 런타임\)이 시작될 때 구성 파일을 제공하는 방법, 관리되지 않는 호스팅 API를 사용하는 방법, 관리되는 코드를 사용하는 방법 또는 ARM ETW 이벤트를 수신하는 방법이 있습니다.  
  
 ARM은 활성화되는 즉시 프로세스의 모든 응용 프로그램 도메인에 대한 데이터를 수집하기 시작합니다.  ARM이 활성화되기 전에 응용 프로그램 도메인이 만들어진 경우 누적 데이터는 응용 프로그램 도메인이 시작된 때가 아닌 ARM이 활성화된 때부터 시작됩니다. 일단 활성화된 ARM은 비활성화할 수 없습니다.  
  
-   CLR 시작 시 ARM을 활성화하려면[\<appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) 요소를 구성 파일에 추가하고 `enabled` 특성을 `true`로 설정합니다.  기본값인 `false`는 해당 ARM이 시작 시에 활성화되지 않는다는 것을 의미할 뿐입니다. 다른 활성화 메커니즘 중 하나를 사용하여 나중에 활성화할 수 있습니다.  
  
-   호스트는 [ICLRAppDomainResourceMonitor](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 호스팅 인터페이스를 요청하여 ARM을 활성화할 수 있습니다.  이 인터페이스가 성공적으로 획득되면 ARM이 활성화됩니다.  
  
-   관리 코드에서는 static\(Visual Basic의 경우 `Shared`\) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName> 속성을 `true`로 설정하여 ARM을 활성화할 수 있습니다.  이 속성이 설정되는 즉시 ARM이 활성화됩니다.  
  
-   시작 후 ETW 이벤트를 수신하여 ARM을 활성화할 수 있습니다.  `AppDomainResourceManagementKeyword` 키워드를 사용하여 공용 공급자 `Microsoft-Windows-DotNETRuntime`을 활성화하면 ARM이 활성화되어 모든 응용 프로그램 도메인에 대한 이벤트를 발생시키기 시작합니다.  데이터를 응용 프로그램 도메인 및 스레드와 연결하려면 `ThreadingKeyword` 키워드로 `Microsoft-Windows-DotNETRuntimeRundown` 공급자도 활성화해야 합니다.  
  
## ARM 사용  
 ARM은 응용 프로그램 도메인에서 사용한 총 프로세서 시간과 메모리 사용에 대한 세 가지 종류의 정보를 제공합니다.  
  
-   **응용 프로그램 도메인에 대한 총 프로세서 시간\(초\)**: 이는 응용 프로그램 도메인 내에서 도메인의 수명 동안 실행에 시간을 소비한 모든 스레드에 대해 운영 체제에서 보고한 스레드 시간을 더해 계산됩니다.  차단되거나 대기 중인 스레드는 프로세서 시간을 사용하지 않습니다.  스레드가 네이티브 코드를 호출하면 네이티브 코드에서 스레드가 소비한 시간은 호출이 발생한 응용 프로그램 도메인에 대한 계산에 포함됩니다.  
  
    -   관리되는 API: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=fullName> 속성  
  
    -   호스팅 API: [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../Topic/ICLRAppDomainResourceMonitor::GetCurrentCpuTime%20Method.md) 메서드  
  
    -   ETW 이벤트: `ThreadCreated`, `ThreadAppDomainEnter` 및 `ThreadTerminated` 이벤트  공급자 및 키워드에 대한 자세한 내용은 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)의 "AppDomain 리소스 모니터링 이벤트"를 참조하십시오.  
  
-   **응용 프로그램 도메인이 수명 동안 수행한 총 관리되는 할당\(바이트\)**: 할당된 개체의 수명이 짧을 수 있으므로 총 할당이 항상 응용 프로그램의 메모리 사용을 반영하지는 않습니다.  그러나 응용 프로그램에서 많은 수의 개체를 할당하고 해제하는 경우 할당 비용이 커질 수 있습니다.  
  
    -   관리되는 API: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=fullName> 속성  
  
    -   호스팅 API: [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../Topic/ICLRAppDomainResourceMonitor::GetCurrentAllocated%20Method.md) 메서드  
  
    -   ETW 이벤트: `AppDomainMemAllocated` 이벤트, `Allocated` 필드  
  
-   **응용 프로그램 도메인에 의해 참조되며 최근의 전체 차단 수집 후에도 남아 있는 관리되는 메모리\(바이트\)**: 이 수는 전체 차단 수집 후에만 정확합니다. 이는 백그라운드에서 수행되면서 응용 프로그램을 차단하지 않는 동시 수집과 대비되는 부분입니다. 예를 들어, <xref:System.GC.Collect?displayProperty=fullName> 메서드 오버로드는 전체 차단 수집을 유발합니다.  
  
    -   관리되는 API: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=fullName> 속성  
  
    -   호스팅 API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md) 메서드, `pAppDomainBytesSurvived` 매개 변수  
  
    -   ETW 이벤트: `AppDomainMemSurvived` 이벤트, `Survived` 필드  
  
-   **프로세스에 의해 참조되며 최근의 전체 차단 수집 후에도 남아 있는 총 관리되는 메모리\(바이트\)**: 개별 응용 프로그램에 대해 유지된 메모리를 이 수와 비교할 수 있습니다.  
  
    -   관리되는 API: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=fullName> 속성  
  
    -   호스팅 API: [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md) 메서드, `pTotalBytesSurvived` 매개 변수  
  
    -   ETW 이벤트: `AppDomainMemSurvived` 이벤트, `ProcessSurvived` 필드  
  
### 전체 차단 수집이 발생하는 시점 확인  
 남은 메모리에 대한 계산이 정확한 시점을 판단하려면 전체 차단 수집이 발생한 직후 이를 알아야 합니다.  이를 수행하기 위한 메서드는 ARM 통계를 검사하는 데 사용하는 API에 따라 다릅니다.  
  
#### 관리되는 API  
 <xref:System.AppDomain> 클래스의 속성을 사용하는 경우 <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=fullName> 메서드를 사용하여 전체 수집 알림에 등록할 수 있습니다.  수집의 접근이 아닌 수집의 완료를 대기하는 것이므로 사용하는 임계값은 중요하지 않습니다.  그런 다음 전체 수집이 완료될 때까지 차단되는 <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=fullName> 메서드를 호출할 수 있습니다.  루프에서 메서드를 호출하고 메서드가 반환될 때마다 필요한 분석을 수행하는 스레드를 만들 수 있습니다.  
  
 또는 정기적으로 <xref:System.GC.CollectionCount%2A?displayProperty=fullName> 메서드를 호출하여 2세대 수집의 수가 증가했는지 볼 수 있습니다.  폴링 빈도에 따라 이 방법은 전체 수집 발생을 나타내는 지표로서 정확하지 않을 수 있습니다.  
  
#### 호스팅 API  
 관리되지 않는 호스팅 API를 사용하는 경우 호스트는 CLR에 [IHostGCManager](../../../ocs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) 인터페이스 구현을 전달해야 합니다.  CLR은 수집이 발생하는 동안 일시 중지된 스레드의 실행을 다시 시작할 때 [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) 메서드를 호출합니다.  CLR은 완료된 수집의 세대를 메서드의 매개 변수로 전달하여 호스트에서 수집이 전체 수집이었는지 부분 수집이었는지를 판단할 수 있도록 합니다.  [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) 메서드 구현은 남은 메모리를 쿼리하여 수가 업데이트된 직후 검색되도록 보장할 수 있습니다.  
  
## 참고 항목  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [ICLRAppDomainResourceMonitor 인터페이스](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)   
 [\<appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)   
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)