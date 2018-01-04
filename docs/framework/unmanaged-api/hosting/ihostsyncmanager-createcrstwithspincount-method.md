---
title: "IHostSyncManager::CreateCrstWithSpinCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31830f97cff1c302ee573b8248eb1d83e696ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a>IHostSyncManager::CreateCrstWithSpinCount 메서드
동기화에 대 한 스핀 카운트 임계 영역 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSpinCount`  
 [in] 임계 영역 개체의 스핀 수를 지정합니다.  
  
 `ppCrst`  
 [out] 주소에 대 한 포인터는 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스에 지정 하거나 임계 영역을 만들 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`CreateCrstWithSpinCount`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|요청 된 중요 한 섹션을 만들 메모리가 충분 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 스핀 수는 다중 프로세서 시스템 에서만 사용 됩니다. 스핀 수 호출 스레드를 사용할 수 없는 임계 연관 된 도달한 세마포에 대해 대기 작업을 수행 하기 전에 회전 해야 하는 횟수를 지정 합니다. 임계 영역 회전 작업 중에 무료 되 면 호출 스레드가 대기 작업을 방지 합니다. `CreateCrstWithSpinCount`Win32 미러링 `InitializeCriticalSectionAndSpinCount` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSemaphore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
