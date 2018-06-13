---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58e7b3e76d90e9e43f3f5259c52b52cd9f8e1f6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455077"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드
"입력", "둡니다" 및 "tailcall" 관리 되는 함수의 후크에서 호출 되는 프로파일러 구현 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFuncEnter`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) 콜백 합니다.  
  
 `pFuncLeave`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) 콜백 합니다.  
  
 `pFuncTailcall`  
 [in] 로 사용 하는 구현에 대 한 포인터는 [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) 콜백 합니다.  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0에서는 각 함수 포인터 해당 해당 콜백 사용 하지 않으려면 null 일 수 있습니다.  
  
 한 번에 하나의 집합만 콜백 활성화할 수 있습니다. 따라서 프로파일러 둘 다를 호출 하는 경우 `SetEnterLeaveFunctionHooks` 및 [icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), 다음 `SetEnterLeaveFunctionHooks2` 우선적으로 적용 합니다.  
  
 `SetEnterLeaveFunctionHooks` 프로파일러의 에서만 메서드를 호출할 수 있습니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
