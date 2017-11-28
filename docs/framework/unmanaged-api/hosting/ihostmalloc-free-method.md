---
title: "IHostMAlloc::Free 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.Free
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ac361f939a134aa6d2bc8b215c5d447b352466e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmallocfree-method"></a>IHostMAlloc::Free 메서드
사용 하 여 할당 된 메모리를 해제는 [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMem`  
 [in] 해제할 메모리에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Free`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|HOST_E_INVALIDOPERATION|호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.|  
  
## <a name="remarks"></a>설명  
 경우는 `pMem` 매개 변수 참조에 대 한 호출을 사용 하 여 할당 되지 않은 메모리 영역 `Alloc`, 호스트 HOST_E_INVALIDOPERATION 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
