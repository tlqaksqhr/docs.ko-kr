---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드
[.NET Framework 4.7 이상 버전에서 지원 됨]  
  
동적 메서드의 JIT 컴파일 시작 될 때마다 프로파일러를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
[in] `functionId`  
컴파일을 시작 되는 JIT에 대 한 메모리 함수의 식별자입니다.   

[in] `fIsSafeToBlock`   
`true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시을 나타내기 위해 `false` 차단는 영향을 주지 않는지 런타임에 작업을 나타냅니다.  

[in] `pILHeader`    
메서드의 IL 헤더의 첫 번째 바이트에 대 한 포인터입니다.   

[in] `cbILHeader`    
IL 헤더의 바이트 수입니다. 

## <a name="remarks"></a>설명  

이 콜백은 동적 메서드가 JIT 컴파일된 있을 때마다 트리거됩니다. 다양 한 IL 스텁 및 LCG 메서드를 포함 합니다. 목표는 사용자에 게 컴파일된 메서드를 식별 하는 충분 한 정보가 프로파일러 작성자를 제공 합니다.

> [!NOTE]
> `functionId` 동적 메서드는 메타 데이터가 때문에 해당 메타 데이터 토큰에 해결 하려면 값을 사용할 수 없습니다.

`pILHeader` 포인터는 콜백 중에 유효 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>참고 항목  
 [DynamicMethodJITCompilationFinished 메서드](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [ICorProfilerCallback8 인터페이스](icorprofilercallback8-interface.md)
