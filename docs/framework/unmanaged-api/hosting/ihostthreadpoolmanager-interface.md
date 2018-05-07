---
title: IHostThreadPoolManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92097cdf735630f3537296f188bd83ea8162add2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager 인터페이스
공용 언어 런타임 (CLR) 스레드 풀을 구성 하 고 스레드 풀에 작업 항목 큐에 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAvailableThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수를 가져옵니다.|  
|[GetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|스레드 풀에 동시에 호스트를 유지 하는 스레드의 최대 수를 가져옵니다.|  
|[GetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|요청에 대비 하 여에서 호스트를 유지 관리 하는 유휴 상태 스레드의 최소 개수를 가져옵니다.|  
|[QueueUserWorkItem 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|실행을 위한 함수 큐 대기 하 고 함수에서 사용할 데이터를 포함 하는 개체를 제공 합니다.|  
|[SetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|최대 스레드 풀에서 호스트를 유지할 수 있는 스레드 수를 설정 합니다.|  
|[SetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|요청에 대비 하 여에서 호스트를 유지 해야 하는 유휴 상태 스레드의 최소 개수를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트에 대 한 호출에 지정 된 값을 사용 하 여 스레드 풀을 구성 하지 않아도 됩니다는 `SetMaxThreads` 및 `SetMinThreads` 메서드. 이 경우 호스트는 이러한 방법 중에서 E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
