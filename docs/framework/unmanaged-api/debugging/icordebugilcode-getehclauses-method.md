---
title: "ICorDebugILCode::GetEHClauses 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode.GetEHClauses
api_location: mscordbi.dll
api_type: COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39d30ef572423d8cb988c074971de095f1709e8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcodegetehclauses-method"></a>ICorDebugILCode::GetEHClauses 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 IL(중간 언어)에 대해 정의된 EH(예외 처리) 절 목록에 대한 포인터를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cClauses`  
 [in] `clauses` 배열의 저장소 용량입니다. 자세한 내용은 설명 부분을 참조하십시오.  
  
 `pcClauses`  
 [out] `clauses` 배열에 관련 정보가 기록되는 절의 수입니다.  
  
 clauses  
 [out] 배열을 [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) 예외 처리 절이이 IL에 대해 정의 된에 대 한 정보를 포함 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 경우 `cClauses` 0 및 `pcClauses` 이 아닌**null**, `pcClauses` 사용 가능한 예외 처리 절의 수로 설정 합니다. `cClauses`는 값이 0이 아닌 경우 `clauses` 배열의 저장소 용량을 나타냅니다. 메서드가 반환될 때 `clauses`는 `cClauses` 항목의 최대값을 포함하며 `pcClauses`는 `clauses` 배열에 실제로 기록된 절의 수로 설정됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugILCode 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [CorDebugEHClause 구조](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
