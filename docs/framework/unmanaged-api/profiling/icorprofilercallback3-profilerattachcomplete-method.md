---
title: ICorProfilerCallback3::ProfilerAttachComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8397900e2dafb69807417090cbb30c85dd884c59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454380"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>ICorProfilerCallback3::ProfilerAttachComplete 메서드
공용 언어 런타임 (CLR)를 나타내는 프로파일러가 이제 호출할 수에 의해 호출 된 [icorprofilerinfo3:: Enumjitedfunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 및 [icorprofilerinfo3:: Enummodules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) 보완 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>설명  
 `ProfilerAttachComplete` 콜백 후 실행 되는 [icorprofilercallback3:: Initializeforattach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) 메서드를 호출 합니다. 다음을 나타냅니다.  
  
-   `InitializeForAttach`에서 프로파일러가 요청한 콜백이 활성화되었습니다.  
  
-   이제 프로파일러가 누락된 알림에 대해 염려하지 않고 연결된 ID에서 후속 작업을 수행할 수 있습니다.  
  
 CLR은 이 콜백의 반환 값을 무시합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
