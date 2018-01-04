---
title: "프로파일링 환경 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc3d490284e371aefb2de712cb5721b0246caa6a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="setting-up-a-profiling-environment"></a>프로파일링 환경 설정
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]에서 프로파일링이 크게 변경되었습니다.  
  
 관리되는 프로세스(응용 프로그램 또는 서비스)가 시작되면 CLR(공용 언어 런타임)을 로드합니다. CLR이 초기화되면 다음 두 가지 환경 변수를 평가하여 프로세스를 프로파일러에 연결해야 할지를 결정합니다.  
  
-   COR_ENABLE_PROFILING: 이 환경 변수가 있고 1로 설정될 경우에만 CLR이 프로파일러에 연결됩니다.  
  
-   COR_PROFILER: COR_ENABLE_PROFILING 확인에 통과하면 이전에 레지스트리에 저장되었어야 하는 이 CLSID 또는 ProgID를 포함하는 프로파일러에 CLR이 연결됩니다. COR_PROFILER 환경 변수는 다음 두 가지 예제와 같이 문자열로 정의됩니다.  
  
    ```  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 CLR 응용 프로그램을 프로파일링하려면 응용 프로그램을 실행하기 전에 COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정해야 합니다. 또한 프로파일러 DLL이 등록되었는지 확인해야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]부터 프로파일러를 등록할 필요가 없습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0, 3.0 및 3.5 프로파일러를 사용 하 여 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 및 이상 버전에서는 COMPLUS_ProfAPI_ProfilerCompatibilitySetting 환경 변수를 설정 해야 합니다.  
  
## <a name="environment-variable-scope"></a>환경 변수 범위  
 COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정하는 방법에 따라 영향을 미치는 범위가 결정됩니다. 다음 방법의 하나로 이들 변수를 설정할 수 있습니다.  
  
-   변수를 설정 하는 경우는 [icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 호출 된 시간에 실행 중인 응용 프로그램에만 적용 됩니다. 변수는 환경을 상속하는 해당 응용 프로그램에 의해 시작된 기타 응용 프로그램에도 적용됩니다.  
  
-   명령 프롬프트 창에서 변수를 설정하면 해당 창에서 시작된 모든 응용 프로그램에 변수가 적용됩니다.  
  
-   사용자 수준에서 변수를 설정하는 경우 파일 탐색기로 시작하는 모든 응용 프로그램에 해당 변수가 적용됩니다. 변수를 설정하고 나서 연 명령 프롬프트 창에는 이 환경 설정이 포함되고 해당 창에서 시작하는 모든 응용 프로그램도 포함됩니다. 사용자 수준 환경 변수를 설정 하려면 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 **속성**, 클릭는 **고급** 탭을 클릭 **환경 변수**, 변수를 추가 하 고는 **사용자 변수** 목록입니다.  
  
-   컴퓨터 수준에서 변수를 설정하는 경우 해당 컴퓨터에서 시작되는 모든 응용 프로그램에 해당 변수가 적용됩니다. 해당 컴퓨터에서 연 명령 프롬프트 창에는 이 환경 설정이 포함되고 해당 창에서 시작하는 모든 응용 프로그램도 포함됩니다. 즉, 해당 컴퓨터의 모든 관리되는 프로세스가 프로파일러를 사용하여 시작됩니다. 컴퓨터 수준에서 환경 변수를 설정 하려면 마우스 오른쪽 단추로 클릭 **내 컴퓨터**, 클릭 **속성**, 클릭는 **고급** 탭을 클릭 **환경 변수**, 변수를 추가 **시스템 변수** 목록을 연 다음 컴퓨터를 다시 시작 합니다. 다시 시작하고 나면 변수를 시스템 수준에서 사용할 수 있습니다.  
  
 Windows 서비스를 프로파일링할 경우 환경 변수를 설정하고 프로파일러 DLL을 등록하고 나서 컴퓨터를 다시 시작해야 합니다. 이러한 고려 사항에 대 한 자세한 내용은 섹션을 참조 하십시오. [Windows 서비스 프로 파일링](#windows_service)합니다.  
  
## <a name="additional-considerations"></a>추가 고려 사항  
  
-   프로파일러 클래스가 구현 하는 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 및 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) 인터페이스입니다. .NET Framework 버전 2.0에서 프로파일러는 `ICorProfilerCallback2`를 구현해야 합니다. 구현하지 않으면 `ICorProfilerCallback2`가 로드되지 않습니다.  
  
-   특정 환경에서 한 번에 한 프로파일러에서만 프로세스를 프로파일링할 수 있습니다. 두 가지 프로파일러를 서로 다른 환경에서 등록할 수 있지만 각 프로파일러는 개별 프로세스를 프로파일링해야 합니다. 프로파일러는 프로파일링되고 있는 프로세스와 같은 주소 공간으로 매핑되는 in-process COM 서버 DLL로 구현되어야 합니다. 이는 프로파일러가 in-process로 실행됨을 의미합니다. .NET Framework는 다른 형식의 COM 서버를 지원하지 않습니다. 예를 들어 프로파일러가 원격 컴퓨터에서 응용 프로그램을 모니터링하려고 하면 프로파일러가 각 컴퓨터에서 수집기 에이전트를 구현해야 합니다. 이들 에이전트를 결과를 일괄 처리하고 중앙 데이터 수집 컴퓨터에 전달합니다.  
  
-   프로파일러는 in-process로 인스턴스화되는 COM 개체이므로 각 프로파일링된 응용 프로그램에는 자체 프로파일러 복사본이 있습니다. 따라서 단일 프로파일러 인스턴스는 여러 응용 프로그램에서 데이터를 처리할 필요가 없습니다. 그러나 다른 프로파일링된 응용 프로그램에서 로그 파일을 덮어쓰지 않도록 방지하려면 프로파일러의 로깅 코드에 논리를 추가해야 합니다.  
  
## <a name="initializing-the-profiler"></a>프로파일러 초기화  
 두 가지 환경 변수 확인을 모두 통과하면 CLR에서는 COM `CoCreateInstance` 함수와 비슷한 방식으로 프로파일러의 인스턴스를 만듭니다. 프로파일러는 직접 호출을 통해 `CoCreateInstance`에 로드되지 않습니다. 따라서 스레딩 모델을 설정해야 하는 `CoInitialize`가 호출되지 않습니다. CLR은 다음 호출에서 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 프로파일러의 메서드. 이 메서드의 서명은 다음과 같습니다.  
  
```  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 프로파일러 쿼리해야 `pICorProfilerInfoUnk` 에 대 한 프로그램 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 또는 [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) 인터페이스 포인터를 및 프로 파일링 동안 나중에 더 많은 정보를 요청할 수 있도록 저장 합니다.  
  
## <a name="setting-event-notifications"></a>이벤트 알림 설정  
 프로파일러 다음 호출에서 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 에 관심이 것 알림 범주를 지정 하는 메서드. 예를 들어 프로파일러가 함수 시작 및 종료 알림과 가비지 컬렉션 알림에만 관심이 있으면 다음을 지정합니다.  
  
```  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 이 방식으로 알림 마스크를 설정하면 프로파일러는 수신하는 알림을 제한할 수 있습니다. 이 접근 방식을 통해 사용자가 단순 또는 특수 목적용 프로파일러를 빌드할 수 있습니다. 이를 통해 프로파일러가 무시하는 알림을 보내는 데 사용되는 CPU 시간이 감소합니다.  
  
 특정 프로파일러 이벤트는 변경할 수 없습니다. 즉, 이들 이벤트는 `ICorProfilerCallback::Initialize` 콜백에서 설정되고 난 직후에 해제할 수 없고 새 이벤트를 설정할 수 없습니다. 변경할 수 없는 이벤트를 변경하려고 하면 `ICorProfilerInfo::SetEventMask`에서 실패한 HRESULT가 반환됩니다.  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a>Windows 서비스 프로파일링  
 Windows 서비스 프로파일링은 공용 언어 런타임 응용 프로그램 프로파일링과 비슷합니다. 두 가지 프로파일링 작업은 모두 환경 변수를 통해 사용하도록 설정됩니다. 운영 체제가 시작될 때 Windows 서비스가 시작되므로 이 항목의 앞에서 설명한 환경 변수가 이미 있고 시스템이 시작되기 전에 필요한 값으로 설정되어야 합니다. 또한 프로파일링 DLL이 시스템에 등록되어 있어야 합니다.  
  
 the COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정하고 프로파일러 DLL을 등록하고 나서 Windows 서비스가 해당 변경 내용을 감지할 수 있도록 대상 컴퓨터를 다시 시작해야 합니다.  
  
 이 변경을 통해 프로파일링이 시스템 전반에서 사용됩니다. 나중에 실행되는 모든 관리되는 응용 프로그램이 프로파일링되지 않게 하려면 대상 컴퓨터를 다시 사직하고 나서 시스템 환경 변수를 삭제해야 합니다.  
  
 이 방법을 사용하면 모든 CLR 프로세스도 프로파일링됩니다. 프로파일러는 논리를 추가 해야 해당 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 관심 있는 현재 프로세스 인지 여부를 검색 하는 콜백 합니다. 관심이 없으면 프로파일러는 초기화를 수행하지 않고 콜백을 오류로 처리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 개요](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)
