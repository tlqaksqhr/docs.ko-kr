---
title: ICLRTask2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed0d2ff3b64bab026087e13d54314eca86181d8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtask2-interface"></a>ICLRTask2 인터페이스
모든 기능을 제공 된 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인터페이스; 또한 스레드 중단 현재 스레드에서 지연 될 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginPreventAsyncAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|지연 새 스레드 현재 스레드에 대 한 요청을 중단 합니다.|  
|[EndPreventAsyncAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|새 또는 스레드의 스레드 중단 요청을 보류 중인 현재 스레드를 중단 합니다.|  
  
## <a name="remarks"></a>설명  
 `ICLRTask2` 상속는 `ICLRTask` 인터페이스 및 호스트에서 실패 하면 안 되는 코드 영역을 보호 하기 위해 스레드 중단을 지연 시킬 수 있는 메서드를 추가 합니다. 호출 `BeginPreventAsyncAbort` 카운터가 증가 하 고 지연 스레드 중단은 현재 스레드 및 호출에 대 한 `EndPreventAsyncAbort` 감소 것입니다. 에 대 한 호출이 `BeginPreventAsyncAbort` 및 `EndPreventAsyncAbort` 중첩 될 수 있습니다. 카운터는 0 보다 큰,으로 현재 스레드에 대 한 스레드 중단이 지연 됩니다.  
  
 경우에 대 한 호출이 `BeginPreventAsyncAbort` 및 `EndPreventAsyncAbort` 됩니다 하지 않을 스레드 중단 현재 스레드를 전달할 수 없는 상태가 될 때까지 수는 있습니다.  
  
 자체적으로 중단 하는 스레드에 지연이 적용 되지 않습니다.  
  
 이 기능을 통해 노출 되는 기능은 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다. 이러한 메서드를 잘못 사용 하면 VM 지정 되지 않은 동작이 발생할 수 있습니다. 예를 들어 호출 `EndPreventAsyncAbort` 먼저 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전에 때 카운터가 0으로 설정 수 없습니다. 마찬가지로, 내부 카운터 오버플로를 검사 하지 않습니다. 호스트와 VM으로 증가 하기 때문에 필수 한도 초과 하는 경우 결과 동작 지정 되지 않았습니다.  
  
 상속 된 멤버에 대 한 정보에 대 한 `ICLRTask` 와 다른이 인터페이스의 사용에 대 한 참조는 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
