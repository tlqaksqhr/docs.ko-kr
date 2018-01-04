---
title: "ICorDebugObjectEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8edc9273710a843b4e99568097646825fc52a09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenumnext-method"></a>ICorDebugObjectEnum::Next 메서드
현재 위치부터 시작 하는 열거형에서 지정 된 개수의 개체의 상대 가상 주소를 (Rva)를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 개체 수입니다.  
  
 `objects`  
 [out] CORDB_ADDRESS 개체를 가리키는 각각 포인터의 배열입니다.  
  
 `pceltFetched`  
 [out] 실제로 반환 된 개체의 수에 대 한 포인터입니다. 이 값은 null 일 수 있으면 `celt` 하나입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
