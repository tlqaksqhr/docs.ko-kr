---
title: "ICorDebugVariableHome::GetArgumentIndex 메서드"
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
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 739d4d787858f64871269ea9bd467bc49424fbae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome::GetArgumentIndex 메서드
함수 인수 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pArgumentIndex`  
 [out] 인수 인덱스에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 다음 값을 반환 합니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|이 메서드는 유효한 인수 인덱스를 반환 했습니다.|  
|`E_FAIL`|현재 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 인스턴스 지역 변수를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 이 인수에 대 한 메타 데이터를 검색 인수 인덱스를 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugVariableHome 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
