---
title: "ICorDebugFunction2::SetJMCStatus 메서드"
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
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 315e036481f0454bf68b2da9e496c441ee843ba2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus 메서드
내 코드만 5d;에 대 한이 ICorDebugFunction2 함수가 표시 단계별로 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bIsJustMyCode`  
 [in] 로 설정 `true` 사용자 코드; 함수로 표시를 그렇지 설정 `false`합니다.  
  
## <a name="return-values"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|함수를 표시 했습니다.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|디버깅할 수 없는 사용자가 코드로 함수를 표시할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 내 코드만 스텝 퍼에 사용자 코드가 아닌 건너뜁니다. 사용자 코드를 디버깅할 수 있는 코드의 하위 집합 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
