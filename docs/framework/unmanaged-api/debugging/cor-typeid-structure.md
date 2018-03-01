---
title: "COR_TYPEID 구조체"
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
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ca6c9b3b02314843a3eaf01d8cd4a9eac5513efa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeid-structure"></a>COR_TYPEID 구조체
유형 식별자를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`token1`|첫 번째 토큰입니다.|  
|`token2`|두 번째 토큰입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_TYPEID` 구조는 여러 디버깅 메서드를 가비지 수집할 개체에 대 한 정보를 제공 하 여 반환 됩니다. 그 다음 전달할 수 있습니다를 인수로 해당 항목에 대 한 추가 정보를 제공 하는 다른 디버깅 메서드로. 열거 하는 예를 들어 여는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 개체, 개별를 검색할 수 있습니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개별 관리 되는 힙의 개체를 나타내는 개체입니다. 에 전달할 수 있습니다는 `COR_TYPEID` 에서 값의 `COR_HEAPOBJECT.type` 필드를 [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 개체에 대 한 형식 정보를 제공 하는 ICorDebugType 개체를 검색 하는 메서드입니다.  
  
 A `COR_TYPEID` 개체는 불투명 되도록 만들어졌습니다. 개별 필드를 액세스 하거나 조작할 수 해야 합니다. 유일한 사용은으로 제공 되는 식별자로 됩니다는 `out` 차례로 메서드 호출 및 수 있는 매개 변수가 추가 정보를 제공 하는 기타 메서드가에 전달 되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
