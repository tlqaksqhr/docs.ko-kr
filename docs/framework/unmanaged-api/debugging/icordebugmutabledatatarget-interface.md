---
title: "ICorDebugMutableDataTarget 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e638b01b30f7969ac3116c6c2725fb4cb3768a68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget 인터페이스
확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스를 변경할 수 있는 데이터 대상을 지원 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ContinueStatusChanged 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|지정된 스레드에서 해결되지 않은 디버그 이벤트의 연속 상태를 변경합니다.|  
|[SetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.|  
|[WriteVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|대상 프로세스 주소 공간에 메모리를 씁니다.|  
  
## <a name="remarks"></a>설명  
 이 확장에는 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 디버깅 도구는 대상 프로세스 (예: 침투 적 라이브 디버깅을 수행)을 수정 하려는 의해 인터페이스를 구현할 수 있습니다.  
  
 이러한 모든 메서드는 이 인터페이스를 구현하지 않거나 해당 메서드 호출에 실패해도 손실되는 핵심 검사 기반 디버깅 기능이 없다는 점에서 선택적입니다.  이러한 메서드의 모든 실패 `HRESULT`는 ICorDebug 메서드 호출의 `HRESULT`로 전파됩니다.  
  
 단일 ICorDebug 메서드 호출에서 여러 변경이 발생할 수 있으며, 관련 변경이 트랜잭션 방식으로 적용(전체 적용되거나 적용 안 함)되게 하는 메커니즘은 없습니다.  즉, 동일한 ICorDebug 호출에 대한 다른 변경이 성공한 후 특정 변경이 실패할 경우 대상 프로세스가 불일치 상태로 남겨지고 디버깅이 불안정해질 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
