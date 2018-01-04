---
title: "IHostMemoryManager::GetMemoryLoad 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.GetMemoryLoad
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 320881447eed00bf0dfeada0f5fbd224c32dfe96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad 메서드
현재 사용에서 되 고 따라서 호스트에서 보고 있는 실제 메모리의 양을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMemoryLoad`  
 [out] 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대 한 포인터입니다.  
  
 `pAvailableBytes`  
 [out] 공용 언어 런타임 (CLR)를 사용할 수 있는 바이트 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `GetMemoryLoad`Win32 래핑합니다 `GlobalMemoryStatus` 함수입니다. 값 `pMemoryLoad` 해당는 `dwMemoryLoad` 필드에 `MEMORYSTATUS` 에서 반환 된 구조 `GlobalMemoryStatus`합니다.  
  
 런타임은은 가비지 수집기에 대 한 휴리스틱으로 반환 값을 사용 합니다. 예를 들어 호스트에서 사용 중인 메모리의 대부분을 보고 가비지 수집기를 사용할 수 있는 상태가 될 수 있는 메모리 양을 늘리려면 여러 세대에서 수집 하도록 선택할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.GC?displayProperty=nameWithType>  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
