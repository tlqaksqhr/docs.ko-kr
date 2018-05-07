---
title: ICorProfilerFunctionControl::SetCodegenFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43c32d1ce4f804da8980dc0c566a77e5b076661b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags 메서드
하나 이상의 플래그 설정 된 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 다시 컴파일된 함수는-just-in-time (JIT)에 대 한 코드 생성을 제어 하는 열거형입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 [in] 하나 이상의 플래그는 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 열거 합니다.  
  
## <a name="remarks"></a>설명  
 프로파일러를 통해이 인터페이스의 인스턴스를 가져옵니다는 [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 콜백 합니다. `SetCodegenFlags` 프로파일러는 다시 컴파일된 함수에 대 한 코드 생성을 제어를 허용 합니다. 모든 다른 JIT 다시 컴파일 매개 변수를와 마찬가지로 코드 생성 플래그 함수의 모든 인스턴스에 적용 합니다.  
  
 JIT 컴파일러는 함수를 컴파일할 때 다른 소스에서 지정 된 다른 플래그와 함께 이러한 컴파일 플래그를 고려 합니다.  다른 소스는 디버거, 사용 하 여 전역 플래그 설정으로 시작할 때 프로파일러에서 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드 (값을 가진 `COR_PRF_DISABLE_INLINING` 및 `COR_PRF_DISABLE_OPTIMIZATIONS`), 및의 [ Icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 콜백 합니다.  JIT 컴파일러 최적화의 최소 크기를 요청 하는 원본에 대 한 우선 순위를 제공 합니다.  예를 들어, 프로파일러를 지정 하는 경우 `COR_PRF_DISABLE_INLINING` 시작 시 하지만 지정 하지 않습니다 `COR_PRF_CODEGEN_DISABLE_INLINING` 에 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 콜백 인라이닝 여전히 사용할 수 없습니다.  마찬가지로, 프로파일러를 지정 하지 않는 경우 `COR_PRF_CODEGEN_DISABLE_INLINING` 에 `SetCodegenFlags`, 하지만 다음 비활성화를 사용 하 여 인라인 처리는 [icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 인라인 처리 콜백을 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerFunctionControl 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
