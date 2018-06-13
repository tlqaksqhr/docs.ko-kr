---
title: CorCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 468ad1acf55c4d1b4fc2b53730f16ee8630cf19b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444017"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention 열거형
관리 코드에서 수행된 호출 규칙의 형식을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|기본 호출 규칙을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|메서드는 가변 개수의 매개 변수를 사용 하며 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|통화 필드 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|로컬 메서드를 호출 임을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|호출 되는 속성을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|관리 되지 않는 호출을 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|제네릭 메서드 인스턴스를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|64 비트 PInvoke 호출에 가변 개수의 매개 변수를 사용 하는 메서드를 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|잘못 된 4 비트 값에 설명합니다.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|호출 규칙으로 하위 4 비트 설명 되어 나타냅니다.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|최상위 비트를 설명 한다는 사실을 나타냅니다는 `this` 매개 변수입니다.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|나타냅니다는 `this` 서명을에서 명시적으로 설명 하는 매개 변수입니다.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|명시적 개수의 형식 인수를 사용 하 여 제네릭 메서드 시그니처를 나타냅니다. 이 표준 매개 변수 개수를 앞에 붙습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
