---
title: "IHostThreadPoolManager::GetMaxThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads 메서드
스레드 풀에 동시에 호스트를 유지 하는 스레드의 최대 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwMaxWorkerThreads`  
 [out] 스레드 풀에서 호스트를 유지 하는 스레드의 최대 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR (프로세스에 로드 되지 않은 않았거나 상태에는 자신이 없습니다 관리 되는 코드 또는 호출 프로세스가 성공적으로 실행 합니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_NOTIMPL|호스트의 구현을 제공 하지 않는 `GetMaxThreads`합니다.|  
  
## <a name="remarks"></a>설명  
 CLR에서는 `GetMaxThreads` 스레드 풀에 있는 스레드의 총 수를 결정 합니다. [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) 메서드는 작업 항목을 현재 처리 되지 않습니다. 스레드 수를 가져옵니다. 반환된 된 값의 모든 요청은 `pdwMaxWorkerThreads` 매개 변수 중인 스레드가 사용 가능 해질 때까지 대기 합니다.  
  
 호스트의 구현을 제공 하지 않는 경우 `GetMaxThreads`, E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [GetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [SetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [IHostThreadPoolManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
