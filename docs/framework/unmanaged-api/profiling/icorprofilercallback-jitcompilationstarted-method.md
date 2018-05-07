---
title: ICorProfilerCallback::JITCompilationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fa1081afc77c8116d8858c187401555409b4dcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted 메서드
적시에 (JIT) 컴파일러의 함수 컴파일을 시작 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 컴파일을 시작 하는 함수의 ID입니다.  
  
 `fIsSafeToBlock`  
 [in] 차단 여부를 나타내는 프로파일러 값 런타임의 작업에 적용 됩니다. 값은 `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 경우 이렇게 하지 않으면 `false`합니다.  
  
 값이 있지만 `true` 런타임 나쁜 영향을 주지, 프로 파일링 결과 왜곡 시킬 수 있습니다.  
  
## <a name="remarks"></a>설명  
 둘 이상의 쌍을 받을 수는 `JITCompilationStarted` 및 [icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) 생성자를 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스입니다. 예를 들어 JIT 컴파일 메서드 A는 런타임 시작 되기는 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다. 따라서 런타임 JIT 컴파일은 클래스 B에 대 한 생성자 실행 합니다. 생성자가 실행 되는 동안 메서드에 A A를 다시 수 없는 JIT 컴파일된 메서드를 호출을 하면 합니다. 이 시나리오에서 메서드 A의 첫 번째 JIT 컴파일 중단 됩니다. 그러나 JIT 컴파일 메서드 A 번의 시도가 모두 JIT 컴파일 이벤트로 보고 됩니다. 프로파일러를 호출 하 여 Microsoft MSIL (intermediate language) 코드는 메서드에 대 한 대체 하려는 경우는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드를 둘 다에 대해 해야 `JITCompilationStarted` 이벤트, 하지만 동일한 MSIL 블록을 사용할 수 있습니다 모두 합니다.  
  
 프로파일러는 두 스레드 콜백 하 동시에 경우에 JIT 콜백 시퀀스를 지원 해야 합니다. 예를 들어, 호출 스레드가 A `JITCompilationStarted`합니다. 그러나 스레드는 호출 전에 `JITCompilationFinished`, 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) A의 스레드에서 함수 ID로 `JITCompilationStarted` 콜백 합니다. 함수 ID 해야 아직 유효 하지 않은 표시 될 수 있습니다 때문에에 대 한 호출 `JITCompilationFinished` 프로파일러에서 아직 받지 했습니다. 그러나 이와 같은 경우에 함수 ID는 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
