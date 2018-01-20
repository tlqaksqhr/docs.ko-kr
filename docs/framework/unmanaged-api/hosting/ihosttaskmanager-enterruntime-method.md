---
title: "IHostTaskManager::EnterRuntime 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70c9e83311fd7427895e1957d3511a45c47434e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerenterruntime-method"></a>IHostTaskManager::EnterRuntime 메서드
관리 되지 않는 메서드를 호출 하는 플랫폼 호출 메서드를 같은 반환 되는지 실행 제어 공용 언어 런타임 (CLR)를 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`EnterRuntime`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청 된 할당을 완료 하려면 사용할 수 없었습니다.|  
  
## <a name="remarks"></a>설명  
 `EnterRuntime`호스트에 알리기 위해 호출 됩니다는에 대 한 관리 되지 않는 함수를 호출 하 여 이전는 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) 메서드, 실행이 끝나면를 만들었고 런타임에 실행 제어를 반환 합니다.  
  
> [!NOTE]
>  [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) 호스트에 알리기 위해 호출 하는에 대 한 관리 되지 않는 함수를 호출 하 여 이전 `LeaveRuntime` 만들어진, 관리 코드를 호출 하 고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [고급 COM 상호 운용성](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [LeaveRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
