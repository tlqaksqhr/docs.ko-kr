---
title: CorDebugGuidToTypeMapping 구조체
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c803a805da605bd52fd50eb1e292c0e277143d7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugguidtotypemapping-structure"></a>CorDebugGuidToTypeMapping 구조체
지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 해당 ICorDebugType 개체 GUID입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`iid`|캐시 된 GUID [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 유형입니다.|  
|`pType`|캐시 된 유형에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
