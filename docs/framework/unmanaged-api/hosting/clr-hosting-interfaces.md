---
title: "CLR 호스팅 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a>CLR 호스팅 인터페이스
이 섹션에서는 관리 되지 않은 인터페이스 설명 호스트 응용 프로그램에 공용 언어 런타임 (CLR)를 통합 하 사용할 수 있습니다. 정보는.NET Framework 버전 2.0 이상 버전에 적용 됩니다. 이러한 인터페이스는 런타임 버전 1.0 및 1.1에에서 비해 더 많은 요소를 제어 하려면 호스트를 활성화 하 고 CLR 및 호스트의 실행 모델 많은 밀접 하 게 통합을 제공 합니다.  
  
 .NET Framework 버전 1.0 및 1.1에서는 호스팅 모델에서 특정 설정을 구성 하 고 이벤트 알림을 받을 수는 프로세스에 CLR을 로드 하는 관리 되지 않는 호스트를 사용 합니다. 그러나 일반적으로 호스트와 CLR에서에서 실행 되었습니다 독립적으로 해당 프로세스입니다. .NET Framework 버전 2.0 및 이후 버전에서는 새로운 추상화 계층을 다양 한 Win32 어셈블리의 형식에서 현재 제공 되는 리소스를 제공 하 고 호스트를 구성할 수 있는 기능 집합이 확장 호스트를 사용 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 등록 된 이벤트에 대 한 콜백을 수행 하는 메서드를 제공 합니다.  
  
 [IApartmentCallback 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 콜백을 아파트 내에서 수행 하기 위한 메서드를 제공 합니다.  
  
 [IAppDomainBinding 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 런타임에 구성 설정에 대 한 메서드를 제공합니다.  
  
 [ICatalogServices 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 카탈로그 서비스를 위한 메서드를 제공 합니다. (이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)  
  
 [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 호스트와 어셈블리에 대 한 CLR 간의 통신을 지 원하는 메서드를 제공 합니다.  
  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 호스트가 아닌 CLR에서 로드 하는 어셈블리 목록을 관리 합니다.  
  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 액세스 하 고 CLR의 다양 한 측면을 구성 하기 위해 호스트에 대 한 메서드를 제공 합니다.  
  
 [ICLRDebugManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRErrorReportingManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 오류 보고에 대 한 사용자 지정 힙 덤프를 구성 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 호스트 CLR의 가비지 수집 시스템과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRHostBindingPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 호스트를 평가 하 여 어셈블리에 대 한 정책 정보 변경 내용을 적용 하기 위한 메서드를 제공 합니다.  
  
 [ICLRHostProtectionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 호스트를에서 특정 관리 되는 클래스, 메서드, 속성 및 부분적으로 신뢰할 수 있는 코드에서 실행 되는 필드를 차단할 수 있습니다.  
  
 [ICLRIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 호스트가 CLR에 지정 된 I/O 요청의 상태를 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.  
  
 [ICLRMemoryNotificationCallback 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 호스트가 win32과 유사한 방법을 사용 하 여 메모리 부족 상태를 보고할 수 있도록 `CreateMemoryResourceNotification` 함수입니다.  
  
 [ICLROnEventManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 등록 및 CLR 이벤트에 대 한 콜백을 등록 취소 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 정책 오류 및 시간 초과가 발생할 경우 수행할 작업을 지정 하려면 호스트를 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRProbingAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 호스트가 만들거나 해당 id를 이해할 필요 없이 내부에서 clr 어셈블리의 id 정보를 사용 하 여 어셈블리 검색 id를 가져오는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRReferenceAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 파일 또는 스트림에서 만들거나 있는 필요 없이 내부에서 clr 어셈블리 id 데이터를 사용 하 여 참조 되는 어셈블리 집합을 조작 하는 호스트를 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 유사한 기능을 제공 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), 호스트 컨트롤 인터페이스를 설정 하는 추가 메서드를 사용 합니다.  
  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 요청 된 작업에 대 한 정보를 동기화 구현에서 교착 상태를 검색 하는 호스트에 대 한 메서드를 제공 합니다.  
  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 호스트는 CLR의 요청을 만드는 하거나 관련된 작업에 대 한 CLR에 알림을 제공 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 호스트가 있는지 CLR 새 작업 만들기, 현재 실행 중인 작업을 가져오고 설정 언어와 문화권을 작업에 대 한 명시적으로 요청 하 고 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRValidator 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.  
  
 [ICorConfiguration 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 CLR을 구성 하기 위한 메서드를 제공 합니다.  
  
 [ICorThreadpool 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 스레드 풀에 액세스 하기 위한 메서드를 제공 합니다.  
  
 [IDebuggerInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 디버깅 서비스의 상태에 대 한 정보를 얻기 위한 메서드를 제공 합니다.  
  
 [IDebuggerThreadControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 차단 하는 방법에 대 한 호스트에 알리기 및 디버깅 서비스에 의해 스레드 차단 해제에 대 한 메서드를 제공 합니다.  
  
 [IGCHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.  
  
 [IGCHost2 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 제공 된 [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기와를 설정 하려면 0 세대 가비지 수집 시스템의 최대 크기 값 보다 큰 수 있게 해 메서드 `DWORD`합니다.  
  
 [IGCHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 가비지 수집기가 호스트의 가상 메모리 제한을 변경 하려면 요청할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IGCThreadControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 가비지 수집에 대 한 차단 될 수 있는 스레드 일정에 참여 하기 위한 메서드를 제공 합니다.  
  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 호스트는 clr 또는 호스트에 의해 로드 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 호스트 별도로 CLR 어셈블리와 모듈을 로드 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostAutoEvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 호스트에서 구현 하는 자동 재설정 이벤트의 표현을 제공 합니다.  
  
 [IHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 어셈블리 로드를 구성 하 고 호스팅 인터페이스를 호스트에서 지원할 결정 하기 위한 방법을 제공 합니다.  
  
 [IHostCrst 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 스레딩에 대 한 임계 영역 호스트의 표시로 사용 됩니다.  
  
 [IHostGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 호스트의 이벤트는 CLR에서 구현 하는 가비지 수집 메커니즘에 알리는 메서드를 제공 합니다.  
  
 [IHostIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 호스트에서 제공 하는 I/O 완료 포트와 상호 작용 하는 CLR를 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 CLR 힙으로부터 호스트를 통해 세분화 된 할당을 요청을 위한 메서드를 제공 합니다.  
  
 [IHostManualEvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 수동 다시 설정 이벤트의 표현 호스트의 구현을 제공합니다.  
  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 표준 Win32 가상 메모리 함수를 사용 하는 대신 호스트를 통해 가상 메모리를 요청 하는 CLR에 대 한 메서드를 제공 합니다.  
  
 [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 CLR의 경우 수행 하는 동작의 호스트 중단, 제한 시간, 또는 실패를 알리는 메서드를 제공 합니다.  
  
 [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 CLR을 호스트에서 구현 하는 보안 컨텍스트 정보를 유지할 수 있습니다.  
  
 [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 현재 실행 중인 스레드의 보안 컨텍스트 제어 하 고에 액세스할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IHostSemaphore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 호스트에서 구현 되는 세마포 표현을 제공 합니다.  
  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 동기화 기본 형식을 만들 수는 CLR에 대 한 메서드를 제공 합니다.  
  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 작업을 관리 하기 위해 호스트와 통신 하는 CLR를 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 표준 운영 체제 스레드 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 CLR를 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostThreadPoolManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 CLR 스레드 풀을 구성 하 고 스레드 풀에 작업 항목 큐에 대 한 메서드를 제공 합니다.  
  
 [IManagedObject 인터페이스](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 관리 되는 개체를 제어 하기 위한 메서드를 제공 합니다.  
  
 "IObjectHandle"  
 간접 참조에서 래핑 해제 값 방식 마샬링 개체에 대 한 방법을 제공합니다.  
  
 [ITypeName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 형식 이름 정보를 얻기 위한 메서드를 제공 합니다. (이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)  
  
 [ITypeNameBuilder 인터페이스](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 형식 이름을 만들기 위한 메서드를 제공 합니다. (이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)  
  
 [ITypeNameFactory 인터페이스](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 형식 이름을 제거 하기 위한 메서드를 제공 합니다. (이 인터페이스는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)  
  
 "IValidator"  
 이식 가능한 실행 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [사용 되지 않는 CLR 호스팅 인터페이스 및 Coclass](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 .NET Framework 버전 1.0 및 1.1에서에서 제공 하는 호스팅 인터페이스를 설명 하는 항목이 포함 되어 있습니다.  
  
 [4 및 4.5.NET Framework에 추가 된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 제공 하는 호스팅 인터페이스를 설명 하는 항목이 포함 되어는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.
