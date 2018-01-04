---
title: "VariableLocationType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: VariableLocationType
api_location: mscordbi.dll
api_type: COM
f1_keywords: VariableLocationType
helpviewer_keywords: VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ea476ef32b807823108aa2836778da576618214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="variablelocationtype-enumeration"></a>VariableLocationType 열거형
기본 위치에 대 한 유형을 변수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`VLT_REGISTER`|변수가 레지스터입니다.|  
|`VLT_REGISTER_RELATIVE`|변수가 메모리 레지스터 상대 위치입니다.|  
|`VLT_INVALID`|변수는 레지스터 또는 레지스터 상대 메모리 위치에 저장 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 멤버는 `VariableLocationType` 열거형에서 반환 되는 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
