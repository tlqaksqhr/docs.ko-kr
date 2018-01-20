---
title: "ICLRSyncManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f75a9b532e91966d6b0be9ac6602080eac896ed8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager 인터페이스
요청 된 작업에 대 한 정보를 가져오려면 호스트가 동기화 구현에서 교착 상태를 감지 하는 데 사용할 수 있는 메서드를 정의 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|공용 언어 런타임 (CLR) 판독기 및 작성기 잠금에 대해 대기 중인 작업의 집합을 결정 하는 데 호스트에 대 한 반복기를 만들도록 요청 합니다.|  
|[DeleteRWLockOwnerIterator 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|CLR로 호출 하 여 생성 된 반복기 손상 요청 `CreateRWLockOwnerIterator`합니다.|  
|[GetMonitorOwner 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|지정 된 모니터를 소유 하는 작업을 가져옵니다.|  
|[GetRWLockOwnerNext 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|현재 판독기 / 작성기 잠금을 기다리고 있는 다음 작업을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [관리 되는 관리 되지 않는 스레딩](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
