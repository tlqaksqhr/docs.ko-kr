---
title: "ICLRTask::Reset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset 메서드
호스트가 완료 되는 작업을 CLR의 현재 다시 사용할 수 있도록 공용 언어 런타임 (CLR) 알립니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 다른 작업을 나타내는입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fFull`  
 [in] `true`런타임에서 현재와 관련 된 보안 및 로캘 정보 외에도 모든 스레드 관련 정적 값을 다시 설정 해야 하는 경우, `ICLRTask` 인스턴스이거나, `false`합니다.  
  
 값이 `true`, 런타임에 사용 하 여 저장 된 데이터를 다시 설정 <xref:System.Threading.Thread.AllocateDataSlot%2A> 또는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Reset`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다. 성공적으로|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 이전에 만든 CLR을 재활용할 수 `ICLRTask` 반복 해 서 새로운 작업이 해야 할 때마다 새 인스턴스를 만들기의 오버 헤드를 방지 하기 위해 인스턴스. 호스트를 호출 하 여이 기능을 사용 하면 `ICLRTask::Reset` 대신 [iclrtask:: Exittask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) 작업 완료 된 시점입니다. 다음 목록은 요약의 일반적인 수명 주기는 `ICLRTask` 인스턴스:  
  
1.  런타임에서 새 만듭니다 `ICLRTask` 인스턴스.  
  
2.  런타임 호출 [ihosttaskmanager:: Getcurrenttask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) 현재 호스트 작업에 대 한 참조를 얻으려고 합니다.  
  
3.  런타임 호출 [ihosttask:: Setclrtask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) 작업과 새 인스턴스를 연결 하는 호스트 작업 합니다.  
  
4.  작업을 실행 하 고 완료 합니다.  
  
5.  호스트를 호출 하 여 작업을 소멸 시킵니다. `ICLRTask::ExitTask`합니다.  
  
 `Reset`두 가지 방법으로이 시나리오를 변경합니다. 호스트에서는 위의 5 단계에서 `Reset` 클린 상태로 작업을 다시 설정 하려면 다음의 `ICLRTask` 에서 연결 된 인스턴스 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스. 원하는 경우 호스트 캐시할 수도 있습니다는 `IHostTask` 인스턴스 다시 사용할 수 있도록 합니다. 위의 1 단계에서 공용 언어 런타임은 가져옵니다 재활용 된 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서 합니다.  
  
 이 방법은 호스트에 다시 사용할 수 있는 작업자 태스크의 풀도 있는 경우 제대로 작동 합니다. 호스트 중 하나를 제거 하면 해당 `IHostTask` 인스턴스를 해당 제거 됩니다 `ICLRTask` 호출 하 여 `ExitTask`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
