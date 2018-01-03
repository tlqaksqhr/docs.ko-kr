---
title: ICorDebugController Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bde0ef86ff6304c696ad8c68fc81c0a339ed6e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontroller-interface1"></a>ICorDebugController Interface1
<xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|이 메서드는 사용되지 않습니다.|  
|`ICorDebugController::CommitChanges`|이 메서드는 사용되지 않습니다.|  
|[Continue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|관리 되는 스레드를 호출한 후 실행을 계속 [icordebugcontroller:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)합니다.|  
|[Detach 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|프로세스 또는 응용 프로그램 도메인에서 디버거를 분리 합니다.|  
|[EnumerateThreads 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|프로세스에서 현재 관리 되는 스레드에 대 한 열거자를 가져옵니다.|  
|[HasQueuedCallbacks 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|지정 된 스레드에 대 한 모든 관리 되는 콜백이 현재 대기 중인 있는지 여부를 나타내는 값을 가져옵니다.|  
|[IsRunning 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|프로세스의 스레드는 현재 실행에 자유롭게 수 있는지 여부를 나타내는 값을 가져옵니다.|  
|[SetAllThreadsDebugState 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|프로세스에서 모든 관리 되는 스레드의 디버그 상태를 설정합니다.|  
|[Stop 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|프로세스에서 관리 되는 코드를 실행 하는 모든 스레드에서 동시 중지를 수행 합니다.|  
|[Terminate 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|지정된 된 종료 코드가 사용 하 여 프로세스를 종료합니다.|  
  
## <a name="remarks"></a>설명  
 경우 `ICorDebugController` 는 프로세스를 제어 범위는 프로세스의 모든 스레드를 포함 합니다. 경우 `ICorDebugController` 되는 범위에 해당 특정 응용 프로그램 도메인의 스레드만 포함 응용 프로그램 도메인을 제어 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
