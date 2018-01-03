---
title: "ICorDebugMutableDataTarget::SetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 077dfacc62c5bb450bc656c8fc102245d581eccc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
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
 `SetThreadContext` 메서드는 운영 체제에서 정의된 `dwThreadID` 인수로 지정된 스레드에 대한 현재 컨텍스트를 업데이트합니다. 컨텍스트 레코드의 형식으로 표시 되는 플랫폼 따라 사용자가 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드. 이 windows에서 [컨텍스트](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugMutableDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
