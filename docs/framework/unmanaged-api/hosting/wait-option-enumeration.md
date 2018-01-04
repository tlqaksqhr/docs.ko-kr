---
title: "WAIT_OPTION 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAIT_OPTION
api_location: mscoree.dll
api_type: COM
f1_keywords: WAIT_OPTION
helpviewer_keywords: WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 143c191592efe8cfea8049f0dd5dc05a5bd4192f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="waitoption-enumeration"></a>WAIT_OPTION 열거형
공용 언어 런타임 (CLR) 블록에서 요청한 작업 하는 경우 수행할 동작 호스트를 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|CLR에서 호출 하는 경우 작업에 활성화 해야 호스트에 알립니다.는 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 메서드.|  
|`WAIT_MSGPUMP`|스레드가 차단 되는 경우 현재 운영 체제 스레드에 대 한 메시지를 펌프 해야 함을 호스트에 알립니다. 에 대해서만이 값을 지정 하는 런타임에서 <xref:System.Threading.ApartmentState.STA> 스레드입니다.|  
|`WAIT_NOTINDEADLOCK`|지정 된 동기화 요청 된 호스트에 의해 분할할 수 없습니다 호스트에 알립니다. 호스트를 반환할 수 없습니다 즉, `HOST_E_DEADLOCK`합니다.|  
  
## <a name="remarks"></a>설명  
 [ihosttaskmanager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) 및 [ihosttaskmanager:: Switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) 메서드는 모두 이러한 종류의 매개 변수를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
