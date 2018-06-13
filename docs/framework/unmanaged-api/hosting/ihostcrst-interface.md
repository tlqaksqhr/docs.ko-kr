---
title: IHostCrst 인터페이스
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f2ef8299911905d651ad5c3076dc9c74f397f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438921"
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
 `IHostCrst` 공용 언어 런타임 임계 영역, 호스트의 표시와 직접 통신할 수 (CLR)와 같은 Win32 함수를 사용 하는 대신 허용 `EnterCriticalSection` 또는 `LeaveCriticalSection`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
