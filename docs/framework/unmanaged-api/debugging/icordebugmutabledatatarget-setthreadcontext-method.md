---
title: ICorDebugMutableDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3826bacb935652a282eac359170d9b93518e5cd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931800"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext 메서드
스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwThreadID`  
 [in] 운영 체제에서 정의된 스레드 식별자입니다.  
  
 `contextSize`  
 [in] 쓸 `pContext` 버퍼의 크기입니다.  
  
 `pContext`  
 [in] 쓸 바이트에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `SetThreadContext` 메서드는 운영 체제에서 정의된 `dwThreadID` 인수로 지정된 스레드에 대한 현재 컨텍스트를 업데이트합니다. 컨텍스트 레코드의 형식을 나타내는 플랫폼에 의해 결정 됩니다 합니다 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드. Windows에서 [상황에 맞는](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugMutableDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
