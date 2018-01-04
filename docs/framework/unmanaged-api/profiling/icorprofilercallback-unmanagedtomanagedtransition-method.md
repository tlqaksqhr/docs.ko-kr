---
title: "ICorProfilerCallback::UnmanagedToManagedTransition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition 메서드
비관리 코드에서 관리 코드로 전환 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 호출 되는 함수의 ID입니다.  
  
 `reason`  
 [in] 값은 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 전환 비관리 코드에서 관리 코드로 호출으로 인해 또는 관리 되는 하나에서 호출 되는 관리 되지 않는 함수에서 반환 된 오류로 인해 발생 했는지 여부를 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 하는 경우의 값 `reason` COR_PRF_TRANSITION_RETURN은 및 `functionId` null이 아닌 ID는 관리 되지 않는 함수와 이며 됩니다 하지 컴파일된 타임 (JIT) 컴파일러를 사용 하는 함수입니다. 관리 되지 않는 함수 그와 관련 된 이름 및 몇 가지 메타 데이터와 같은 몇 가지 기본 정보를 갖고 있습니다.  
  
 하는 경우의 값 `reason` COR_PRF_TRANSITION_CALL,이 호출된 된 함수 (즉, 관리 되는 함수)가 아직 JIT 컴파일된 수 있기 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ManagedToUnmanagedTransition 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [C++ Interop 사용(암시적 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
