---
title: "CorDebugBlockingObject 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingObject Structure
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingObject
helpviewer_keywords: CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c47735565c960c2600f7274d0d59d5a6ec6c178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 구조체
스레드가 차단 되는 특별 한 이유가 스레드가 차단 되는 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pBlockingObject`|스레드가 차단 되어 개체입니다. 이 개체는 현재 동기화 된 상태의 기간에만 유효 합니다. 스레드가 각각 두를 동일한 동기화 된 상태에서 동일한 개체에 차단 하는 경우 예상 된 [icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) 메서드를 같은 값을 반환 합니다. 그러나 인터페이스 수 또는 포인터에 해당 되지 않을 수 있습니다.|  
|`dwTimeout`|작업을 차단 하기 전에 시간을 밀리초 단위로 시간 제한 또는 제한 시간이 초과 되지 않음을 나타내는 INFINITE 값 됩니다. 시간 제한 값은 남아 있는 시간이 아닌 차단 작업에 대 한 시간의 총 길이 지정 합니다.|  
|`blockingReason`|이 개체에서 스레드가 차단 되는 이유입니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
