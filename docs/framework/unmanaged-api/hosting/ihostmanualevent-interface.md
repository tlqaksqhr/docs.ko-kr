---
title: "IHostManualEvent 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c19125d96d5f4a9e91fc083d53f36ebebd2c569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent 인터페이스
수동 다시 설정 이벤트의 표현 호스트의 구현을 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|현재 다시 설정 `IHostManualEvent` 인스턴스 신호 되지 않은 상태로 합니다.|  
|[Set 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|에서는 현재 `IHostManualEvent` 인스턴스 신호를 받은 상태로 있습니다.|  
|[Wait 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|현재 `IHostManualEvent` 가 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostAutoEvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [IHostSemaphore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
