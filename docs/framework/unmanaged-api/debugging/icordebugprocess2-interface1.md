---
title: ICorDebugProcess2 Interface1
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
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80f6c35ba2ef2ec74293d0f025ddf20254f504a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2-interface1"></a>ICorDebugProcess2 Interface1
관리 코드를 실행 하는 프로세스를 나타내는 ICorDebugProcess 인터페이스를 논리적으로 확장 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|지정 된 오프셋에 대 한 이전 호출에 의해 설정 된 중단점을 제거 `ICorDebugProcess2::SetUnmanagedBreakpoint`합니다.|  
|[GetDesiredNGENCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|이 참조 하는 프로세스에 이미지를 로드 하는 공용 언어 런타임 (CLR)에 대 한 설정 해야 하는 플래그를 가져옵니다 `ICorDebugProcess2`합니다.|  
|[GetReferenceValueFromGCHandle 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|가비지 수집을 처리 하는 지정된 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.|  
|[GetThreadForTaskID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|지정한 식별자를 가진 작업이 실행 되는 스레드를 가져옵니다.|  
|[GetVersion 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|디버깅 중인 프로세스가 실행 되는 CLR의 버전을 가져옵니다.|  
|[SetDesiredNGENCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|디버깅 중인 프로세스에 이미지를 로드 하 여 적시에 (JIT) 컴파일러에 필요한 플래그를 설정 합니다.|  
|[SetUnmanagedBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|네이티브 이미지를 지정 된 오프셋 위치에서 관리 되지 않는 중단점을 설정합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
