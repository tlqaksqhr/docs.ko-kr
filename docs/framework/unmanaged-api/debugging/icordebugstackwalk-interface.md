---
title: ICorDebugStackWalk 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 612e0f84302d5bee6479264ef2dbba4c7152657e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk 인터페이스
스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|현재 프레임에 대 한 컨텍스트를 반환 합니다.는 `ICorDebugStackWalk` 개체입니다.|  
|[SetContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|설정의 `ICorDebugStackWalk` 개체의 현재 컨텍스트 스레드에 대 한 올바른 컨텍스트를 합니다.|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|이동 된 `ICorDebugStackWalk` 다음 프레임으로 개체입니다.|  
|[GetFrame 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|현재 프레임의 가져옵니다는 `ICorDebugStackWalk` 개체입니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
