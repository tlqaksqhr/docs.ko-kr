---
title: "CorSerializationType 열거형"
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
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e43151b1611f5b9b8218d30ba46a9143f463c193
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corserializationtype-enumeration"></a>CorSerializationType 열거형
공용 언어 런타임에서 개체가 serialize 되는 방식을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|개체의 serialization 정의 되지 않습니다.|  
|`SERIALIZATION_TYPE_BOOLEAN`|Boolean 형식의 개체를 serialize|  
|`SERIALIZATION_TYPE_CHAR`|개체가 문자 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I1`|부호 있는 1 바이트 정수로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U1`|부호 없는 1 바이트 정수로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I2`|부호 있는 2 바이트 정수 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U2`|부호 없는 2 바이트 정수인 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I4`|부호 있는 4 바이트 정수로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U4`|부호 없는 4 바이트 정수로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_I8`|부호 있는 8 바이트 정수 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_U8`|부호 없는 8 바이트 정수로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_R4`|4 바이트 부동 소수점으로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_R8`|8 바이트 부동 소수점으로 개체가 serialize 됩니다.|  
|`SERIALIZATION_TYPE_STRING`|개체가는 System.String 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_SZARRAY`|단일 차원, 개체를 serialize 0 인 배열입니다.|  
|`SERIALIZATION_TYPE_TYPE`|개체가 제네릭 형식으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|개체가는 태그가 지정 된 개체로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_FIELD`|개체가 필드로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_PROPERTY`|개체가 속성으로 serialize 됩니다.|  
|`SERIALIZATION_TYPE_ENUM`|열거형으로 개체가 serialize 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
