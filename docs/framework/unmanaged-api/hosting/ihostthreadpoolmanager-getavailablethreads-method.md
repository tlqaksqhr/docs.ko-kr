---
title: "IHostThreadPoolManager::GetAvailableThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetAvailableThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11cd8de264a332cd553ad44a35355bf45039ab84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a>IHostThreadPoolManager::GetAvailableThreads 메서드
작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwAvailableWorkerThreads`  
 [out] 작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetAvailableThreads`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_NOTIMPL|호스트의 구현을 제공 하지 않는 `GetAvailableThreads`합니다.|  
  
## <a name="remarks"></a>설명  
 호스트의 구현을 제공 하지 않는 경우 `GetAvailableThreads`, E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [IHostThreadPoolManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
