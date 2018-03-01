---
title: "FunctionIDMapper 함수"
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
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 24e48ecb551a5faacc7da94b857b2e260f5aeca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper-function"></a>FunctionIDMapper 함수
지정 된 식별자는 함수에 사용할 대체 ID에 다시 매핑할 수는 프로파일러에 알립니다.는 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), 및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 해당 함수에 대 한 콜백을 합니다. `FunctionIDMapper`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `funcId`  
 [in] 다시 매핑할 함수 식별자입니다.  
  
 `pbHookFunction`  
 [out] 프로파일러를 설정 하는 값에 대 한 포인터 `true` 받으려는 경우 `FunctionEnter2`, `FunctionLeave2`, 및 `FunctionTailcall2` 콜백을;이 값을 설정, `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다. `false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다. 그렇지 않은 경우 null 반환 값에서 프로세스 중지를 포함 하 여 예기치 않은 결과가 만들어집니다.  
  
## <a name="remarks"></a>설명  
 `FunctionIDMapper` 는 콜백 함수입니다. 함수 ID 프로파일러에 대 한 더 유용한 다른 식별자를 매핑할 프로파일러에 의해 구현 됩니다. `FunctionIDMapper` 지정된 된 함수에 사용할 대체 ID를 반환 합니다. 그런 다음 실행 엔진에서 프로파일러를 다시 기존의 함수 ID 외에도이 대체 ID를 전달 하 여 프로파일러 요청을 인식는 `clientData` 의 매개 변수는 `FunctionEnter2`, `FunctionLeave2`, 및 `FunctionTailcall2` 후크를 식별 하려면 호출 되 고 후크 하는 함수입니다.  
  
 사용할 수는 [icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) 의 구현을 지정 하는 메서드는 `FunctionIDMapper` 함수입니다. 호출할 수 있습니다는 `ICorProfilerInfo::SetFunctionIDMapper` 메서드를 한 번만 않으며이 권장에서 수행 하는 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.  
  
 기본적으로 가정 하는 프로파일러 하는 플래그를 설정 COR_PRF_MONITOR_ENTERLEAVE를 사용 하 여 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)를 통해 후크를 설정 하 고 [icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), 받아야 하는 `FunctionEnter2`, `FunctionLeave2`, 및 `FunctionTailcall2` 모든 함수에 대 한 콜백을 합니다. 그러나 프로파일러를 구현할 수 있습니다 `FunctionIDMapper` 선택적으로 특정 이러한 콜백을 수신를 방지 하기 위해 설정 하 여 함수 `pbHookFunction` 를 `false`합니다.  
  
 프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드에서 동시에 동일한 메서드/함수 호출 하는 사례를 허용할 수 있어야 합니다. 이러한 경우 프로파일러에는 여러 나타날 수 `FunctionIDMapper` 동일에 대 한 콜백을 `FunctionID`합니다. 프로파일러에서 되어야 같은 여러 번 호출 될 때 동일한 값이이 콜백에서 반환 `FunctionID`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [SetFunctionIDMapper 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [FunctionIDMapper2 함수](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
