---
title: "IHostTaskManager::LeaveRuntime 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4c168cffba44a21d6705e8abd921ecbf8a9da6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime 메서드
현재 실행 중인 작업이 공용 언어 런타임 (CLR) 종료 하 고 관리 되지 않는 코드를 입력 되려고 함을 호스트에 알립니다.  
  
> [!IMPORTANT]
>  해당 호출 [ihosttaskmanager:: Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) 현재 실행 중인 작업은 관리 코드를 다시 입력 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `target`  
 [in] 관리 되지 않는 함수를 호출할 수의 매핑된 이식 가능한 실행 파일 내 주소입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청 된 할당을 사용할 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 비관리 코드에서 호출 시퀀스를 중첩할 수 있습니다. 아래 목록에는 가상의 상황을 설명 하는 예를 들어 호출의 시퀀스 `LeaveRuntime`, [ihosttaskmanager:: Reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [ihosttaskmanager:: Reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), 및 `IHostTaskManager::EnterRuntime` 중첩 된 레이어를 식별 하는 호스트 수 있습니다.  
  
|작업|해당 메서드 호출|  
|------------|-------------------------------|  
|관리 되는 Visual Basic 실행 호출 플랫폼을 사용 하 여 C에서 작성 하는 관리 되지 않는 함수 호출 됩니다.|`IHostTaskManager::LeaveRuntime`|  
|관리 되지 않는 C 함수는 C#으로 작성 된 관리 되는 DLL의 메서드를 호출 합니다.|`IHostTaskManager::ReverseEnterRuntime`|  
|관리 되는 C# 함수 호출 또한 플랫폼을 사용 하 여 C로 작성 된 다른 관리 되지 않는 함수를 호출 합니다.|`IHostTaskManager::LeaveRuntime`|  
|두 번째 관리 되지 않는 함수는 C# 함수를 실행을 반환합니다.|`IHostTaskManager::EnterRuntime`|  
|C# 함수는 첫 번째 관리 되지 않는 함수 실행을 반환합니다.|`IHostTaskManager::ReverseLeaveRuntime`|  
|첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램 실행 제어를 반환 합니다.|`IHostTaskManager::EnterRuntime`|  
  
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
