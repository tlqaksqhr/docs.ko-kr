---
title: ICorDebugBreakpoint Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 220cd1a41ed69325b557e6498a511865b78817ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugbreakpoint-interface1"></a>ICorDebugBreakpoint Interface1
함수 또는 값에 대 한 조사식 위치에 중단점을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Activate 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|이 활성 상태를 설정 `ICorDebugBreakpoint`합니다.|  
|[IsActive 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|나타내는 값을 가져옵니다 여부이 `ICorDebugBreakpoint` 활성화 되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 중단점 조건 식을 직접 지원 하지 않습니다. 디버거 위에 구현 해야 이러한 기능을 사용할 경우 `ICorDebugBreakpoint`합니다.  
  
 ICorDebugFunctionBreakpoint 인터페이스 확장 `ICorDebugBreakpoint` 함수에서 중단점을 지원 하도록 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
