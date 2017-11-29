---
title: "ETaskType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ETaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ETaskType
helpviewer_keywords: ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52e027c5d2ead70bbd624fafe3021121557cd261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="etasktype-enumeration"></a>ETaskType 열거형
로 표시 되는 작업의 유형을 나타내는 값을 포함 한 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 또는 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`TT_ADUNLOAD`|인터페이스는 응용 프로그램 도메인 언로드 작업을 나타냅니다.|  
|`TT_DEBUGGERHELPER`|디버거 도우미 작업을 나타냅니다.|  
|`TT_FINALIZER`|종료자 작업을 나타냅니다.|  
|`TT_GC`|가비지 수집 작업을 나타냅니다.|  
|`TT_THREADPOOL_GATE`|게이트 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_IOCOMPLETION`|I/O 스레드 작업 또는 완료 포트 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_TIMER`|타이머 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_WAIT`|대기 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_WORKER`|작업자 스레드 작업을 나타냅니다.|  
|`TT_UNKNOWN`|알 수 없는 작업입니다.|  
|`TT_USER`|사용자 작업을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
