---
title: "ICorProfilerCallback::ManagedToUnmanagedTransition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ManagedToUnmanagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59e36f9285f57b54935e40243e87d44b687686da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>ICorProfilerCallback::ManagedToUnmanagedTransition 메서드
관리 코드에서 비관리 코드로 전환 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 호출 되는 함수의 ID입니다.  
  
 `reason`  
 [in] 값은 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 전환 관리 코드에서 비관리 코드로 호출으로 인해 또는 관리 되는 함수에 의해 관리 되지 않는 호출에서 반환 된 오류로 인해 발생 했는지 여부를 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 하는 경우의 값 `reason` COR_PRF_TRANSITION_CALL, 함수는 관리 되지 않는 함수는 됩니다 하지 컴파일된-just-in-time 컴파일러를 사용 하 여 ID가 됩니다. 관리 되지 않는 함수 그와 관련 된 이름 및 몇 가지 메타 데이터와 같은 기본 정보를 갖고 있습니다. 암시적 플랫폼을 사용 하 여 관리 되지 않는 함수가 호출 되 면 호출 (PInvoke), 런타임에서 호출의 대상 및 값을 확인할 수 없습니다 `functionId` null이 됩니다. 암시적 PInvoke에 대 한 자세한 내용은 참조 하십시오. [c + + Interop를 사용 하 여 (암시적 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [UnmanagedToManagedTransition 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [C++에서 명시적 PInvoke 사용(DllImport 특성)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
