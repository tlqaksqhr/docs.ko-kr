---
title: "ICorDebugModule2::SetJMCStatus 메서드"
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
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a461a9c05b18de45426247743c6e4ffca775025a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus 메서드
모든 클래스의 모든 메서드의 코드 JMC (내) 상태에서 제외 하 고 지정 된 값이 ICorDebugModule2 설정는 `pTokens` 반대 값을 설정 하는 배열입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bIsJustMycode`  
 [in] 로 설정 `true` 로 설정 하는 코드가 디버깅 필요가 없으면 이면 `false`합니다.  
  
 `cTokens`  
 [in] `pTokens` 배열의 크기입니다.  
  
 `pTokens`  
 [in] 배열을 `mdToken` 값으로 설정 된 JMC 상태에 있는 메서드를 참조 하며 각!`bIsJustMycode`합니다.  
  
## <a name="remarks"></a>설명  
 에 지정 된 각 방법의 JMC 상태는 `pTokens` 배열은의 반대로 설정 되는 `bIsJustMycode` 값입니다. 이 모듈의 다른 모든 메서드에 상태가 설정 되 고 `bIsJustMycode` 값입니다.  
  
 `SetJMCStatus` 메서드는이 모듈의 모든 이전 JMC 설정을 지웁니다.  
  
 `SetJMCStatus` 모든 기능을 성공적으로 설정 된 경우 메서드는 s_ok이 고 HRESULT를 반환 합니다. 표시 된 함수는 일부 경우 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT 반환 `true` 디버깅 가능 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
