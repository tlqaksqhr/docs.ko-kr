---
title: "ICorProfilerCallback::RemotingClientInvocationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 071e2892202271cac5e0acb226e9bef0e626b134
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a>ICorProfilerCallback::RemotingClientInvocationStarted 메서드
한 원격 호출이 시작 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a>설명  
 이 이벤트는 동기 및 비동기 호출에 대해 동일 합니다.  
  
 다음 콜백 쌍의 각 항목은 동일한 스레드에서 발생 합니다.  
  
-   `RemotingClientInvocationStarted`및 [icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 및 [icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 및 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 원격 콜백와 관련 된 다음 문제를 알고 있어야 합니다.  
  
-   원격 함수가 실행 하므로 클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림을 올바르게 수신 되지 않습니다 프로파일러 API에서 반영 되지 않았습니다. 프록시 개체;를 통해 발생 하는 실제로 호출 프로파일러를 특정 함수는 JIT 컴파일 되었지만 사용 되지는 않습니다 나타납니다.  
  
-   프로파일러는 비동기 원격 이벤트에 대 한 정확한 알림을 받지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
