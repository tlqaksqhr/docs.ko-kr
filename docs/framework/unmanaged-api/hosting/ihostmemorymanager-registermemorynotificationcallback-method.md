---
title: "IHostMemoryManager::RegisterMemoryNotificationCallback 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.RegisterMemoryNotificationCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a59de95ea671b6f568ade81005c718cac00350e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>IHostMemoryManager::RegisterMemoryNotificationCallback 메서드
호스트에 공용 언어 런타임 (CLR)를 알리기 위해 호출 하는 콜백 함수에 대 한 포인터는 컴퓨터의 현재 메모리 로드를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallback`  
 [in] 에 대 한 인터페이스 포인터는 [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) CLR에서 구현 되는 인스턴스.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 때문에 `ICLRMemoryNotificationCallback` 인터페이스 메서드를 하나만 정의 ([iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), 않기 때문에 `pCallback` 에 대 한 포인터는 `ICLRMemoryNotificationCallback` CLR에서 제공 하는 인스턴스는 등록은 콜백 함수 자체에 대 한 효과적으로 합니다. 호스트에서 호출 `OnMemoryNotification` 표준 Win32 대신 보고서 메모리가 중 상태가 `CreateMemoryResourceNotification` 함수입니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.  
  
> [!NOTE]
>  에 대 한 호출이 `OnMemoryNotification` 를 차단 하지 않도록 합니다. 항상 즉시 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRMemoryNotificationCallback 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
