---
title: "IDENTITY_ATTRIBUTE 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c0d09bf4c24f977a490f946cbc35b2b3f53dfc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE 구조체
에 대 한 메타 데이터 특성 정보를 포함 한 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pszNamespace`|네임 스페이스를 포함 된 null로 끝나는 문자열에 대 한 포인터의 특성이입니다.|  
|`pszName`|특성의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.|  
|`pszValue`|특성의 값이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 `IDENTITY_ATTRIBUTE` 구조 null로 끝나는 문자열에 대 한 세 포인터를 포함 합니다. 이러한 세 가지 문자열 특성이 두 개에 대해 설명 합니다.  
  
 인스턴스는 `IDENTITY_ATTRIBUTE` 구조는의 인스턴스에 연결 되어 있는 [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) 구조입니다. `IDENTITY_ATTRIBUTE` 실제 문자열 및 해당 구조에 포함 된 `IDENTITY_ATTRIBUTE_BLOB` 구조에 나열 된 세 개의 문자열에 대 한 오프셋이 나열 된 `IDENTITY_ATTRIBUTE` 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IDefinitionIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [IDENTITY_ATTRIBUTE_BLOB 구조체](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
