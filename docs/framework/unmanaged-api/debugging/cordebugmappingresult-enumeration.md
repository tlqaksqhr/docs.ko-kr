---
title: "CorDebugMappingResult 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMappingResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMappingResult
helpviewer_keywords: CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 924cfec87b99cba9621af02d4e78e72094060ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult 열거형
IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MAPPING_PROLOG`|네이티브 코드는 프롤로그에 이므로 IP의 값은 0입니다.|  
|`MAPPING_EPILOG`|네이티브 코드는 에필로그는 IP의 값은 메서드의 마지막 명령의 주소입니다.|  
|`MAPPING_NO_INFO`|매핑 정보가 없는 방법에 대해 사용할 수 있는 이므로 IP의 값은 0입니다.|  
|`MAPPING_UNMAPPED_ADDRESS`|메서드에 대 한 매핑 정보를는 없지만 현재 주소 Microsoft MSIL (intermediate language) 코드에 매핑할 수 없습니다. IP의 값은 0입니다.|  
|`MAPPING_EXACT`|MSIL 코드에 정확히 메서드가 매핑되어 있거나 프레임 IP의 값은 정확 하 게 해석 되었으므로 합니다.|  
|`MAPPING_APPROXIMATE`|메서드가 성공적으로 매핑한, 되지만 IP의 값은 근사치일 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 사용할 수는 [icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) 메서드 명령 포인터의 값을 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
