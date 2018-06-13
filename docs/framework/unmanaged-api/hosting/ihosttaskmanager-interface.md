---
title: IHostTaskManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9715738931d1b6a91ad9fae7e00ba607905d380f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449066"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager 인터페이스
공용 언어 런타임 (CLR)에서 표준 운영 체제 스레드 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginDelayAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|호스트 관리 코드에는 현재 작업 중단할 수 없는 기간이 시작 됨을 알립니다.|  
|[BeginThreadAffinity 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 마침표를 시작 하는 코드를 관리 하는 호스트에 알립니다.|  
|[CallNeedsHostHook 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|호스트를에서 공용 언어 런타임에서 관리 되지 않는 함수에 지정된 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있습니다.|  
|[CreateTask 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|호스트에서 새 작업을 만들도록 요청 합니다.|  
|[EndDelayAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|관리 코드는 호스트를 종료 하 고 없는 현재 작업을 중단 하지 말아야, 기간을 호출한 후에 알립니다. `BeginDelayAbort`합니다.|  
|[EndThreadAffinity 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|관리 코드는 호스트를 종료 하 고 없는 현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 기간을 호출한 후에 알립니다. `BeginThreadAffinity`합니다.|  
|[EnterRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|관리 되지 않는 메서드를 호출 하는 플랫폼 호출 메서드를 같은 반환 되는지 실행 제어 CLR을 호스트에 알립니다.|  
|[GetCurrentTask 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|이 호출이 수행 된 운영 체제 스레드에 대해 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetStackGuarantee 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|스택 공간이 스택 작업이 완료 된 후 사용 가능 하도록 보장 하지만 프로세스의 닫기 전에 크기를 가져옵니다.|  
|[LeaveRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|관리 코드는 호스트를 관리 되지 않는 함수를 호출 하려고에 알립니다.|  
|[ReverseEnterRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|비관리 코드에서 공용 언어 런타임 (CLR)로 호출이 수행 되는 호스트에 알립니다.|  
|[ReverseLeaveRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|제어를 차례로 호출 된 관리 코드에서 관리 되지 않는 함수는 clr에서 호스트에 알립니다.|  
|[SetCLRTaskManager 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|호스트에 대 한 인터페이스 포인터에 제공 된 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 인스턴스는 CLR에서 구현 합니다.|  
|[SetLocale 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|CLR이는 현재 작업에서 로캘을 변경 되었음을 호스트에 알립니다.|  
|[SetStackGuarantee 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|내부용으로 예약되어 있습니다.|  
|[SetUILocale 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|현재 작업에서 사용자 인터페이스 로캘이 변경 되었음을 호스트에 알립니다.|  
|[Sleep 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|현재 작업 절전 모드로 전환 됨 호스트에 알립니다.|  
|[SwitchToTask 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|현재 작업에서 전환 해야 함을 호스트에 알립니다.|  
  
## <a name="remarks"></a>설명  
 `IHostTaskManager` CLR을 만들고 작업을 관리할 수 있습니다 후크 제어가에서 비관리 코드로 마샬링하거나 그 반대로 하는 경우 작업을 수행 하 고 특정 동작을 지정 하는 호스트를 제공 하는 호스트 수 및 코드 실행 하는 동안 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
