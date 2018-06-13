---
title: CorDebugBlockingReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5e1267b619d5900ed9af55dd6079a8f38d6550
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406902"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason 열거형
지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`BLOCKING_NONE`|내부 전용입니다.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|스레드 임계 연결 된 개체에 대 한 모니터 잠금과 획득 하려고 합니다. 중 하나를 호출 하는 경우 일반적으로 발생이 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 메서드.|  
|`BLOCKING_MONITOR_EVENT`|스레드가 개체에 대 한 모니터 잠금과와 연결 하는 이벤트를 기다리고 있습니다. 중 하나를 호출 하는 경우 일반적으로 발생이 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` 메서드.|  
  
## <a name="remarks"></a>설명  
 때는 `BLOCKING_MONITOR_CRITICAL_SECTION` 또는 `BLOCKING_MONITOR_EVENT` 멤버에 사용 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조는 `pBlockingObject` 구조 가리키는 입력 되 고 개체를 나타내는 "ICorDebugValue" 인터페이스의 멤버 . 구현 보장도 [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
