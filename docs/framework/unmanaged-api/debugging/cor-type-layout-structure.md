---
title: COR_TYPE_LAYOUT 구조체
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88a7b0672e15097c60afbe069ce5b78bd5c38d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cortypelayout-structure"></a>COR_TYPE_LAYOUT 구조체
메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`parentID`|이 형식에 대 한 부모 형식의 식별자입니다. NULL 유형 id (token1 = 0, token2 = 0)의 형식 id에 해당 하는 경우 <xref:System.Object?displayProperty=nameWithType>합니다.|  
|`objectSize`|이 형식의 개체의 기본 크기입니다. 비 변수 크기의 개체에 대 한 총 크기입니다.|  
|`numFields`|이 형식의 개체에 포함 된 필드의 수입니다.|  
|`boxOffset`|Box은이 이와 같은 경우 개체의 필드의 시작 오프셋입니다. 이 필드는 기본 형식 및 구조와 같은 값 형식에 대해서만 유효 합니다.|  
|`type`|이 형식이 속해 있는 CorElementType 합니다.|  
  
## <a name="remarks"></a>설명  
 경우 `numFields` 0 보다 크면 호출할 수 있습니다는 [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) 이 형식의 필드에 대 한 정보를 얻는 메서드를 합니다. 경우 `type` 은 `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, 또는 `ELEMENT_TYPE_SZARRAY`,이 형식의 개체의 크기는 변수가 아니며 전달할 수 있습니다는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 구조체는 [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
