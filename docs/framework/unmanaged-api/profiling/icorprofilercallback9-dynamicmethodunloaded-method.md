---
title: ICorProfilerCallback9::DynamicMethodUnloaded 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452405"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9::DynamicMethodUnloaded 메서드
[.NET Framework 4.7.2 이상 버전에서 지원 됨]  
  
동적 메서드는 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a>매개 변수  
[in] `functionId`  
가비지 수집 되 고 언로드된 된 메모리에서 함수 식별자입니다.   

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[ICorProfilerCallback8.DynamicMethodJITCompilationStarted 메서드](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[ICorProfilerCallback8.DynamicMethodJITCompilationFinished 메서드](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
[ICorProfilerCallback9 인터페이스](icorprofilercallback9-interface.md)   
[COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
