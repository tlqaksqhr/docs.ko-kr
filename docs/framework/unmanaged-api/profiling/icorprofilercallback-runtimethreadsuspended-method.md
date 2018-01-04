---
title: "ICorProfilerCallback::RuntimeThreadSuspended 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadSuspended
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f22e9a6ed8c62256bb3e614dbc1278dea24d4e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended 메서드
지정된 된 스레드가 일시 중단 됨 또는 일시 중단 하려고 합니다. 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadId`  
 [in] 일시 중단 된 스레드의 ID입니다.  
  
## <a name="remarks"></a>설명  
 `RuntimeThreadSuspended` 알림이 사이의 든 지 발생할 수 있습니다는 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 및 연결 된 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다. 간에 발생 하는 알림 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 및 `RuntimeResumeStarted` 실행 중이 던에서 스레드가 비관리 코드 및 런타임에 진입할 때 일시 중단 된 됩니다.  
  
 일반적으로이 콜백에서 스레드가 일시 중단 된 직후에 발생 합니다. 그러나 현재 실행 중인 스레드 (이 콜백을 호출한 스레드)를 일시 중단 된 경우이 콜백을 스레드가 일시 중단 하기 바로 전에 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeThreadResumed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
