---
title: "IHostCrst 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a>IHostCrst 인터페이스
스레딩에 대 한 임계 영역 호스트의 표시로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Enter 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|임계 영역을 입력합니다.|  
|[Leave 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|임계 영역을 유지합니다.|  
|[SetSpinCount 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|임계 영역에 대 한 스핀 수를 설정합니다.|  
|[TryEnter 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|임계 영역 및 보고서 성공 또는 실패를 즉시 입력 하려고 합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostCrst`공용 언어 런타임 임계 영역, 호스트의 표시와 직접 통신할 수 (CLR)와 같은 Win32 함수를 사용 하는 대신 허용 `EnterCriticalSection` 또는 `LeaveCriticalSection`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
