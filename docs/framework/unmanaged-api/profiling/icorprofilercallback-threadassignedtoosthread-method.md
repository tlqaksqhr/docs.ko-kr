---
title: "ICorProfilerCallback::ThreadAssignedToOSThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadAssignedToOSThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42c23a8190ea611d0333ebd96a31428574191b23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a>ICorProfilerCallback::ThreadAssignedToOSThread 메서드
관리 되는 스레드는 특정 운영 체제 스레드를 사용 하 여 구현 되 고 있음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `managedThreadId`  
 [in] 관리 되는 스레드의 식별자입니다.  
  
 `osThreadId`  
 [in] 운영 체제 스레드의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 `ThreadAssignedToOSThread` 프로파일러 파이버 관리 되는 스레드는 운영 체제 스레드 간에 정확한 매핑을 유지할 수 있도록 콜백 존재 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
