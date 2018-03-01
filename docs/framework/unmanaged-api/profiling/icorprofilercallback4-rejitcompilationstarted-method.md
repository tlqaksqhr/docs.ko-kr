---
title: "ICorProfilerCallback4::ReJITCompilationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted 메서드
적시에 (JIT) 컴파일러는 함수를 다시 시작 했습니다 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] JIT 컴파일러를 다시 컴파일하려면 시작 되는 함수의 ID입니다.  
  
 `rejitId`  
 [in] 다시 컴파일이 ID 새 버전의 함수입니다.  
  
 `fIsSafeToBlock`  
 [in] `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 있는지 나타내려면 `false` 차단는 영향을 주지 않는지 런타임에 작업을 나타냅니다. 값이 `true` 런타임에 대해, 영향을 주지 않으며 하지만 프로 파일링 결과 영향을 줄 수 있습니다.  
  
## <a name="remarks"></a>설명  
 둘 이상의 쌍을 받을 수는 `ReJITCompilationStarted` 및 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스 생성자입니다. 예를 들어 런타임에 메서드 A를 다시 컴파일하려면 시작 되기는 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다. 따라서 런타임 클래스 B에 대 한 생성자를 다시 컴파일 및 실행 합니다. 생성자가 실행 되는 동안 A 메서드 A 다시 컴파일해야 하는 메서드를 호출을 하면 합니다. 이 시나리오에서 메서드 A의 첫 번째 다시 컴파일이 중단 됩니다. 그러나 둘 다 JIT 다시 컴파일 이벤트와 함께 A가 보고 하는 메서드를 다시 시도 합니다.  
  
 프로파일러는 두 스레드 콜백 하 동시에 경우에 JIT 다시 컴파일 콜백의 시퀀스를 지원 해야 합니다. 예를 들어, 호출 스레드가 A `ReJITCompilationStarted`; 있으 나 먼저 스레드 A 호출 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) 함수 ID로 `ReJITCompilationStarted` A. 스레드에 대 한 콜백 함수 ID 해야 아직 유효 하지 않은 표시 될 수 있습니다 때문에에 대 한 호출 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 프로파일러에서 아직 받지 했습니다. 그러나이 경우 함수 ID는 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [ReJITCompilationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
