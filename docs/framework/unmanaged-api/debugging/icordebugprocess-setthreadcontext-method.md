---
title: "ICorDebugProcess::SetThreadContext 메서드"
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
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext 메서드
이 프로세스에서 지정 된 스레드의 컨텍스트를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `threadID`  
 [in] 컨텍스트를 설정 하는 대 한 스레드의 ID입니다.  
  
 `contextSize`  
 [in] `context` 배열의 크기입니다.  
  
 `context`  
 [in] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.  
  
 컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 디버거에서 Win32 대신이 메서드를 호출 해야 `SetThreadContext` 는 스레드는 실제로는 해당 컨텍스트가 일시적으로 변경 된 "도용된" 상태에 있을 때문에 작동 합니다. 스레드가 네이티브 코드에 있을 때만이 메서드를 사용 해야 합니다. 사용 하 여 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 관리 코드의 스레드에 대 한 합니다. 밴드의 범위를 벗어난 (OOB) 디버그 이벤트 중의 스레드 컨텍스트를 수정할 필요가 해야 합니다.  
  
 전달 되는 데이터는 현재 플랫폼에 대 한 상황에 맞는 구조 여야 합니다.  
  
 이 메서드는 제대로 사용 하지 않으면 런타임을 손상 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
