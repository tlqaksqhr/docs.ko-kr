---
title: "ICorDebugType2::GetTypeID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugType2.GetTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d18aa8210ea90736c0757e2587aab4ff143dcdad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2::GetTypeID 메서드
가져옵니다는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 형식에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 [out] 에 대 한 포인터는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 ICorDebugType에 대 한 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다. `HRESULT` 코드는 다음과 같습니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|`S_OK`|메서드가 정상적으로 실행되었습니다. 메서드는 유효한 검색 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)합니다.|  
|`CORDBG_E_CLASS_NOT_LOADED`|형식 로드 되지 않았습니다.|  
|`CORDBG_E_UNSUPPORTED`|형식이 지원 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 매핑을 수도 수 로드 되었을 런타임에 있는 형식을 나타내는 ICorDebugType에서 제공 된 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), 런타임에 로드 형식을 식별 하는 불투명으로 사용 하는 처리 합니다.  
  
 경우는 ICorDebugType 나타내는 형식이 아직이 메서드가 반환 로드 `CORDBG_E_CLASS_NOT_LOADED`합니다.  반환 형식을 지원 되지 않는 경우 `CORDBG_E_UNSUPPORTED`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugType2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
