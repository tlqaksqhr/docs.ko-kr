---
title: "ICorProfilerCallback2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2
helpviewer_keywords: ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4d1afed1aefbdd8a2733697c342fcf7aafabd8f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 인터페이스
프로파일러가 구독 하려는 이벤트가 발생할 때 코드 프로파일러에 알리기 위해 공용 언어 런타임 (CLR)에서 사용 되는 메서드를 제공 합니다. `ICorProfilerCallback2` 인터페이스의 확장은 여 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다. 즉,.NET Framework 버전 2.0에에서 도입 된 새 콜백을 제공 합니다.  
  
> [!NOTE]
>  각 메서드 구현은 HRESULT 값 실패 시 성공 또는 E_FAIL에 s_ok이 고 값을 반환 해야 합니다. CLR에서 제외 하 고 각 콜백에 의해 반환 되는 HRESULT를 무시 하는 현재 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[FinalizeableObjectQueued 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|종료자 스레드는 실행할 수 있도록 종료자 인 개체가 이미 대기열 코드 프로파일러에 알립니다. 해당 `Finalize` 메서드.|  
|[GarbageCollectionFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|가비지 수집이 완료 되 고 해당 되는 모든 가비지 수집 콜백이 실행 되었음을 프로파일러에 알립니다.|  
|[GarbageCollectionStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|가비지 수집이 시작에 코드 프로파일러에 알립니다.|  
|[HandleCreated 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|가비지 컬렉션 핸들을 이미 만들었다고 코드 프로파일러에 알립니다.|  
|[HandleDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|가비지 컬렉션 핸들이 제거 된 코드 프로파일러에 알립니다.|  
|[RootReferences2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|가비지 컬렉션이 발생 한 후 루트 참조에 대 한 프로파일러를 알립니다. 이 메서드는의 확장은 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 메서드.|  
|[SurvivingReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|에서는 가비지 수집에서 남은 개체 참조에 대 한 프로파일러를 알립니다.|  
|[ThreadNameChanged 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|스레드 이름이 변경 된 코드 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>설명  
 메서드를 호출 하는 CLR의 `ICorProfilerCallback` (또는 `ICorProfilerCallback2`) 면 구독에 프로파일러 하는 이벤트를 프로파일러에 알리는 인터페이스를 발생 합니다. CLR 코드 프로파일러와 통신 하는 기본 콜백 인터페이스입니다.  
  
 코드 프로파일러가의 메서드를 구현 해야 합니다는 `ICorProfilerCallback` 인터페이스입니다. .NET Framework 2.0 및 이후 버전에서는 대 한 프로파일러 구현 해야 합니다는 `ICorProfilerCallback2` 메서드. 각 메서드 구현은 HRESULT 값 실패 시 성공 또는 E_FAIL에 s_ok이 고 값을 반환 해야 합니다. CLR에서 제외 하 고 각 콜백에 의해 반환 되는 HRESULT를 무시 하는 현재 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)합니다.  
  
 Microsoft Windows 레지스트리, 구현 하는 COM 개체에에서 등록 해야 코드 프로파일러는 `ICorProfilerCallback` 및 `ICorProfilerCallback2` 인터페이스입니다. 호출 하 여 알림을 받고 싶은 이벤트를 구독 하는 코드 프로파일러 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)합니다. 이렇게 하려면 보통의 구현에서 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)합니다. 프로파일러는 다음 이벤트가 발생 하려고 하거나 실행 중인 런타임 프로세스에서 발생 한 직후 때 런타임에서 알림을 받을 수 있습니다.  
  
> [!NOTE]
>  프로파일러는 단일 COM 개체를 등록합니다. 프로파일러는.NET Framework 버전 1.0 또는 1.1을 대상으로 지정 하는 경우 해당 COM 개체의 메서드를 구현만 필요한 `ICorProfilerCallback`합니다. 이상 버전에서는 COM 개체가 구현 해야의 메서드 및.NET Framework 버전 2.0 대상으로 하는 경우 `ICorProfilerCallback2`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로 파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
