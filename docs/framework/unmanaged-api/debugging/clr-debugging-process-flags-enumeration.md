---
title: CLR_DEBUGGING_PROCESS_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff6b245c80050a5e85561b8bba6aa9ba8199ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="clrdebuggingprocessflags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS 열거형
사용 되는 값을 제공 된 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|이 런타임 보낼 catch 업 아닌 관리 되는 디버거 이벤트를 있습니다. 따라잡기 및 catch 업 비 이벤트 간의 차이 대 한 설명 섹션을 참조 하십시오.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|보류 중인 관리 되는 이벤트는 한 <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 요청 합니다.|  
  
## <a name="remarks"></a>설명  
 후속 이벤트는 프로세스, 응용 프로그램 도메인, 어셈블리, 모듈 및 프로세스에 연결에 디버거가 현재 상태로 전환 하는 스레드 만들기 알림이 포함 됩니다. 비 catch 업 이벤트도 표시 하는 `CLR_DEBUGGING_MANAGED_EVENT_PENDING` 플래그입니다. 모든 다른 디버거 이벤트, 예외 등을 포함 하 고 관리 디버깅 도우미 (MDA) 알림입니다.  
  
 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` 플래그를 사용 하면 런타임 예외를 종료 하 고 취소할 수 있는 관리 되는 디버거가 연결 요청을 구분할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Metahost.idl, Metahost.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
