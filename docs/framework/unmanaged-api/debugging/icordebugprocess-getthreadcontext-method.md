---
title: ICorDebugProcess::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea977b1ccecf9de5a04e1f1127658ca6c15043a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext 메서드
이 프로세스에서 지정 된 스레드의 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadID`  
 [in] 컨텍스트를 검색 하려는 스레드의 ID입니다.  
  
 `contextSize`  
 [in] `context` 배열의 크기입니다.  
  
 `context`  
 [out에서] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.  
  
 컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 디버거에서 Win32 대신이 메서드를 호출 해야 `GetThreadContext` 메서드는 스레드는 실제로는 해당 컨텍스트가 일시적으로 변경 된 "도용된" 상태에 있을 때문에 있습니다. 스레드가 네이티브 코드에 있을 때만이 메서드를 사용 해야 합니다. 사용 하 여 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 관리 코드의 스레드에 대 한 합니다.  
  
 반환 되는 데이터는 현재 플랫폼에 대 한 상황에 맞는 구조입니다. Win32와 마찬가지로 `GetThreadContext` 호출자에 게 초기화 메서드는 `context` 이 메서드를 호출 하기 전에 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
