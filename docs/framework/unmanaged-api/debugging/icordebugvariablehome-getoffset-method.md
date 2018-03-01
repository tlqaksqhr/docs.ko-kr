---
title: "ICorDebugVariableHome::GetOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f80a362d4b44d13c39218b9d7a0db11ef49f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome::GetOffset 메서드
변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pOffset`  
 [out] 기본 레지스터 오프셋입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 다음 값을 반환합니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|변수가 메모리 레지스터 상대 위치입니다.|  
|`E_FAIL`|변수는 레지스터 상대 메모리 위치에 없는 경우|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugVariableHome 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
