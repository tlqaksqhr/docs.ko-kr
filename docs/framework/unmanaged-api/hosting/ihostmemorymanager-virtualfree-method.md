---
title: "IHostMemoryManager::VirtualFree 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualFree
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 663c01d7e4b551ecf18bdd85a63aefc43f9750e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree 메서드
해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다. Win32 구현은 `VirtualFree` 해제, 커밋 또는 해제 하 고 커밋 호출 프로세스의 가상 주소 공간 내에 있는 페이지의 영역입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lpAddress`  
 [in] 해제 될 가상 메모리 페이지의 기본 주소에 대 한 포인터입니다.  
  
 `dwSize`  
 [in] 바이트 해제에 영역의 크기입니다.  
  
 `dwFreeType`  
 [in] 해제 작업의 형식입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualFree`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|HOST_E_INVALIDOPERATION|호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.|  
  
## <a name="remarks"></a>설명  
 `VirtualFree`연결 된 가상 메모리 페이지를 실행 하는 해제는 `lpAddress` 한 이전 호출을 통해 매개 변수는 [ihostmemorymanager:: Virtualalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) 함수입니다. 호스트를 통해 할당 되지 않은 메모리를 해제 하려고 HOST_E_INVALIDOPERATION 반환 해야 합니다.  
  
 의미 체계는 동일 하 게의 Win32 구현의 `VirtualFree`합니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
