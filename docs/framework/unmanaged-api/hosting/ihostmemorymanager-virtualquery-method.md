---
title: "IHostMemoryManager::VirtualQuery 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualQuery
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fd893cd92f7e7621aefe59595cfd9905bc77afd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery 메서드
해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다. Win32 구현은 `VirtualQuery` 호출 프로세스의 가상 주소 공간에 있는 페이지의 범위에 대 한 정보를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lpAddress`  
 [in] 쿼리할 수 있는 가상 메모리의 주소에 대 한 포인터입니다.  
  
 `lpBuffer`  
 [out] 지정 된 메모리 영역에 대 한 정보를 포함 하는 구조에 대 한 포인터입니다.  
  
 `dwLength`  
 [in] 버퍼를 바이트 단위로 크기는 `lpBuffer` 를 가리킵니다.  
  
 `pResult`  
 [out] 정보 버퍼에 의해 반환 된 바이트 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualQuery`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `VirtualQuery`호출 프로세스의 가상 주소 공간에 있는 페이지의 범위에 대 한 정보를 제공합니다. 값을 설정 하는이 구현에서 `pResult` 바이트 수로 매개 변수 정보 버퍼에 반환 되 고 HRESULT 값을 반환 합니다. Win32에서 `VirtualQuery` 함수, 반환 값은 버퍼 크기입니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.  
  
> [!IMPORTANT]
>  운영 체제의 구현 `VirtualQuery` 교착 상태를 유발 하지 않으므로 및 임의의 스레드가 사용자 코드에서 일시 중단 된 상태로 실행을 완료할 수 있습니다. 이 방법의 호스팅된 버전을 구현할 때 주의 기울여야를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
