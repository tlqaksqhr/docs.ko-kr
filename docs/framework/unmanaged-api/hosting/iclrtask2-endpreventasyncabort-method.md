---
title: "ICLRTask2::EndPreventAsyncAbort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.EndPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c76a75004b4593e8e93aa4dd999c85c0fb7cf38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a>ICLRTask2::EndPreventAsyncAbort 메서드
새 또는 스레드의 스레드 중단 요청을 보류 중인 현재 스레드를 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|HOST_E_INVALIDOPERATION|메서드는 현재 스레드의 되지 않는 스레드에서 호출 되었습니다.|  
  
## <a name="remarks"></a>설명  
 현재 스레드에 대 한 하나에서이 메서드는 지연 스레드 중단 감소 카운터를 호출 합니다.  
  
 에 대 한 호출이 [iclrtask2:: Beginpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) 및 `EndPreventAsyncAbort` 중첩 될 수 있습니다. 카운터는 0 보다 큰,으로 현재 스레드에 대 한 스레드 중단이 지연 됩니다.  
  
 이 기능을 통해 노출 되는 기능은 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다. 이러한 메서드를 잘못 사용 하면 VM 지정 되지 않은 동작이 발생할 수 있습니다. 예를 들어 호출 `EndPreventAsyncAbort` 먼저 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전에 때 카운터가 0으로 설정 수 없습니다. 마찬가지로, 내부 카운터 오버플로를 검사 하지 않습니다. 호스트와 VM으로 증가 하기 때문에 필수 한도 초과 하는 경우 결과 동작 지정 되지 않았습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [BeginPreventAsyncAbort 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [ICLRTask2 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
