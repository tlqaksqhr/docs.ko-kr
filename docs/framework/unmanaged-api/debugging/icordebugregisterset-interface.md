---
title: "ICorDebugRegisterSet 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 714f3d7839ce1d8b65405b6cb3c91d43f1db6642
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet 인터페이스
현재 코드를 실행 하는 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRegisters 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|(현재 코드를 실행 하는 컴퓨터)에서 각 레지스터의 값을 가져옵니다는 비트 마스크에 의해 지정 된 합니다.|  
|[GetRegistersAvailable 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|비트 마스크를 가져옵니다가 있는 레지스터를 나타내는 `ICorDebugRegisterSet` 현재 사용할 수 있습니다.|  
|[GetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|현재 스레드의 컨텍스트를 가져옵니다.|  
|[SetRegisters 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|.NET Framework 버전 2.0에 대 한 구현 되지 않습니다.|  
|[SetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|.NET Framework 2.0에 대 한 구현 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugRegisterSet` 인터페이스는 32 비트 레지스터를 지원 합니다. 사용 하 여는 [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) 추가 레지스터를 필요로 하는 i A 64와 같은 플랫폼에 대 한 인터페이스입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
