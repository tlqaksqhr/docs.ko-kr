---
title: "ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c460cfd24a83ca2a6c75e061b7a797c8f455bc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 메서드
업데이트 된 버전의 "입력", "둡니다" 및 "tailcall" 후크 관리 되는 함수에서 호출 되도록 하는 프로파일러 구현 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFuncEnter`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 콜백 합니다.  
  
 `pFuncLeave`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 콜백 합니다.  
  
 `pFuncTailcall`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 콜백 합니다.  
  
## <a name="remarks"></a>설명  
 `SetEnterLeaveFunctionHooks2` 메서드는 비슷합니다는 [icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) 메서드. 전자를 사용할 enter/두십시오/tailcall 콜백의 이전 버전으로 사용할 함수를 지정 하려면 enter/두십시오/tailcall 콜백 및 후자의 최신 버전으로 사용할 함수를 지정 합니다.  
  
 한 번에 하나의 집합만 콜백 활성화할 수 있습니다. 따라서 프로파일러 둘 다를 호출 하는 경우 `ICorProfilerInfo::SetEnterLeaveFunctionHooks` 및 `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` 사용 됩니다.  
  
 `SetEnterLeaveFunctionHooks2` 프로파일러의 에서만 메서드를 호출할 수 있습니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
