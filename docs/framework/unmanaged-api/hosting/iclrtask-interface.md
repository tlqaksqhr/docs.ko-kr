---
title: ICLRTask 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba53e4af114773a347d15b7308dc4c3567154e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtask-interface"></a>ICLRTask 인터페이스
호스트 공용 언어 런타임 (CLR)의 요청을 만들기 위해 하거나 관련된 작업에 대 한 CLR에 알림을 제공 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Abort 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|CLR 작업을 중단 하도록 요청 하는 현재 `ICLRTask` 인스턴스가 나타내는입니다.|  
|[ExitTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|작업이 현재 연결 CLR 알립니다 `ICLRTask` 인스턴스가 종료 되 고 작업 종료 하려고 합니다.|  
|[GetMemStats 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|현재 태스크에 의해 메모리 리소스의 사용에 대 한 통계 정보를 가져옵니다 `ICLRTask` 인스턴스.|  
|[LocksHeld 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|작업에서 현재 보유 중인 잠금 수를 가져옵니다.|  
|[NeedsPriorityScheduling 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|호스트 현재 작업을 재조정 하기 위해 높은 우선 순위를 할당 해야 하는지 여부를 나타내는 값을 가져옵니다 `ICLRTask` 인스턴스.|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|호스트가 완료 되는 작업을 CLR의 현재 다시 사용할 수 있도록 CLR 알립니다 `ICLRTask` 인스턴스를 다른 작업을 나타내는입니다.|  
|[RudeAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|CLR을 현재 작업을 중단 하면 `ICLRTask` 종료 자가 실행 될 보장 하지 않고 즉시 인스턴스.|  
|[SetTaskIdentifier 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|현재 작업에 대 한 고유 식별자를 설정 `ICLRTask` 디버깅에서 사용 하기 위해 인스턴스.|  
|[SwitchIn 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|현재 나타내는 작업이 CLR 알립니다 `ICLRTask` 인스턴스가 가능한 상태입니다.|  
|[SwitchOut 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|현재 나타내는 작업이 CLR 알립니다 `ICLRTask` 인스턴스는 더 이상 작동 가능한 상태가 됩니다.|  
|[YieldTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|다른 작업에 사용할 수 있는 CLR 확인 프로세서 시간 요청합니다. CLR은 작업 처리 시간 양보할 수 있는 상태에 놓이게 됩니다 하지 않을 수도 있습니다.|  
  
## <a name="remarks"></a>설명  
 `ICLRTask` CLR에 대 한 작업의 표현입니다. 코드 실행 하는 동안 언제 든 지 실행 또는 실행 대기 중인 작업을 설명할 수 있습니다. 호스트에서는 `ICLRTask::SwitchIn` CLR에 알리기 위해 메서드를 작업 하는 현재 `ICLRTask` 인스턴스가 나타내는 작동 가능한 상태가 됩니다. 호출한 후 `ICLRTask::SwitchIn`, 호스트 런타임을 호출 하 여 지정 된 대로 스레드 선호도 필요로 하는 경우에 제외 하 고 운영 체제 스레드에서 작업을 예약할 수는 [ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) 및 [Ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) 메서드. 얼마 후 운영 체제 하 스레드에서 작업을 제거 하 고 실행 중이지 않은 상태로 설정할 수 있습니다. 예를 들어이 태스크는 동기화 기본 형식에서 차단 또는 I/O 작업이 완료 될 때까지 대기 될 때마다 발생할 수 있습니다. 호스트에서는 [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) 현재 나타내는 작업이 CLR에 알리는 `ICLRTask` 인스턴스는 더 이상 가능한 상태입니다.  
  
 작업은 일반적으로 코드 실행의 끝에 종료 합니다. 그 당시 호스트 호출 `ICLRTask::ExitTask` 연결 된 제거할 `ICLRTask`합니다. 하지만 작업을 호출 하 여 재활용할 수도 있습니다 `ICLRTask::Reset`를 허용 하는 `ICLRTask` 인스턴스를 다시 사용할 수 있습니다. 이 방법은 반복 해 서 만들고 인스턴스 제거의 오버 헤드를 방지 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [ICLRTask2 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
