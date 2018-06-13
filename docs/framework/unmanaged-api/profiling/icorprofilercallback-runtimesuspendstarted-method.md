---
title: ICorProfilerCallback::RuntimeSuspendStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1197f066332ee131e4ee18fee6487b78b36e5081
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452773"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted 메서드
런타임에서 모든 런타임 스레드를 일시 중단 하려고 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `suspendReason`  
 [in] 값은 [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) 일시 중단 이유를 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 비관리 코드에 있는 모든 런타임 스레드 다시 런타임에 입력 하려고 시도할 때까지 실행을 계속 수 있습니다. 해당 시점 것도 일시 중단 됩니다 런타임 재개할 때까지 합니다. 런타임에 입력 하는 새 스레드에 적용 됩니다. 런타임에서 모든 스레드는 인터럽트 가능한 코드에 이미 또는 인터럽트 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 되는 경우 즉시 하거나 일시 중단 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [RuntimeSuspendFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
