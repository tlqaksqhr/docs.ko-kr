---
title: IHostMemoryManager::VirtualAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc 메서드
해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다. Win32 구현은 `VirtualAlloc` 예약 하거나 호출 프로세스의 가상 주소 공간에 있는 페이지의 영역을 커밋합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] 할당할 지역의 시작 주소에 대 한 포인터입니다.  
  
 `dwSize`  
 [in] 영역의 바이트 크기입니다.  
  
 `flAllocationType`  
 [in] 메모리 할당의 형식입니다.  
  
 `flProtect`  
 [in] 지역에 대 한 보호를 메모리의 페이지를 할당할 수 있습니다.  
  
 `dwCriticalLevel`  
 [in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 할당 오류의 영향을 나타내는 값입니다.  
  
 `ppMem`  
 [out] 요청을 충족할 수 있는 경우에 null 또는 할당 된 메모리의 시작 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|메모리가 부족 할당 요청을 완료할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 호출 하 여 프로세스의 주소 공간에서 영역을 예약 `VirtualAlloc`합니다. `pAddress` 매개 변수에 사용할 메모리 블록의 시작 주소를 포함 합니다. 이 매개 변수는 일반적으로 설정 하는 null로 합니다. 운영 체제 프로세스에 사용할 수 있는 사용 가능한 주소 범위에 대 한 기록을 유지합니다. A `pAddress` null 값을 판단 되는 영역을 예약 하 고 시스템에 지시 합니다. 또는 메모리 블록에 대 한 특정 시작 주소를 제공할 수 있습니다. 두 경우 모두 출력 매개 변수 `ppMem` 할당된 된 메모리에 대 한 포인터로 반환 됩니다. 함수 자체 HRESULT 값을 반환 합니다.  
  
 Win32 `VirtualAlloc` 함수에는 한 `ppMem` 매개 변수를 대신에 할당된 된 메모리에 포인터를 반환 합니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
