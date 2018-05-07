---
title: IHostSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa9f039cb7eaa7ccd22bad36098c00a697d818d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager 인터페이스
공용 언어 런타임 (CLR) Win32 동기화 기능을 사용 하지 않고 호스트를 호출 하 여 동기화 기본 형식을 만드는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateAutoEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|자동 재설정 이벤트 개체를 만듭니다.|  
|[CreateCrst 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|동기화에 대 한 임계 영역 개체를 만듭니다.|  
|[CreateCrstWithSpinCount 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|동기화에 대 한 스핀 카운트 임계 영역 개체를 만듭니다.|  
|[CreateManualEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|수동 재설정 이벤트 개체를 만듭니다.|  
|[CreateMonitorEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|모니터링 되는 자동 재설정 이벤트 개체를 만듭니다.|  
|[CreateRWLockReaderEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|판독기 잠금 구현에 대 한 수동 재설정 이벤트 개체를 만듭니다.|  
|[CreateRWLockWriterEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|작성기 잠금 구현에 대 한 자동 재설정 이벤트 개체를 만듭니다.|  
|[CreateSemaphore 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|만듭니다는 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 대기 이벤트에 대 한 세마포도 사용할 CLR에 대 한 개체입니다.|  
|[SetCLRSyncManager 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|설정의 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 현재와 연결할 인스턴스 `IHostSyncManager` 인스턴스.|  
  
## <a name="remarks"></a>설명  
 CLR은 호스트의 구현을 검색 `IHostSyncManager` 호출 하 여는 [ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 메서드는 `IID` IID_IHostSyncManager의 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
