---
title: CorElementType Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebe2cf95f5637e6924b85c2389f1c59679580298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449172"
---
# <a name="corelementtype-enumeration1"></a>CorElementType Enumeration1
공용 언어 런타임에서 지정 <xref:System.Type>, 형식 한정자 또는 형식 메타 데이터 서명에 형식에 대 한 정보입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|내부적으로 사용 합니다.|  
|`ELEMENT_TYPE_VOID`|Void 형식입니다.|  
|`ELEMENT_TYPE_BOOLEAN`|Boolean 형식|  
|`ELEMENT_TYPE_CHAR`|문자 형식입니다.|  
|`ELEMENT_TYPE_I1`|부호 있는 1 바이트 정수입니다.|  
|`ELEMENT_TYPE_U1`|부호 없는 1바이트 정수입니다.|  
|`ELEMENT_TYPE_I2`|부호 있는 2 바이트 정수입니다.|  
|`ELEMENT_TYPE_U2`|부호 없는 2 바이트 정수입니다.|  
|`ELEMENT_TYPE_I4`|부호 있는 4 바이트 정수입니다.|  
|`ELEMENT_TYPE_U4`|부호 없는 4 바이트 정수입니다.|  
|`ELEMENT_TYPE_I8`|부호 있는 8 바이트 정수입니다.|  
|`ELEMENT_TYPE_U8`|부호 없는 8 바이트 정수입니다.|  
|`ELEMENT_TYPE_R4`|4 바이트 부동 소수점입니다.|  
|`ELEMENT_TYPE_R8`|8 바이트 부동 소수점입니다.|  
|`ELEMENT_TYPE_STRING`|System.String 형식입니다.|  
|`ELEMENT_TYPE_PTR`|포인터 형식 한정자입니다.|  
|`ELEMENT_TYPE_BYREF`|참조 형식 한정자입니다.|  
|`ELEMENT_TYPE_VALUETYPE`|값 형식 한정자입니다.|  
|`ELEMENT_TYPE_CLASS`|클래스 형식 한정자입니다.|  
|`ELEMENT_TYPE_VAR`|클래스 변수 형식 한정자입니다.|  
|`ELEMENT_TYPE_ARRAY`|다차원 배열 형식 한정자입니다.|  
|`ELEMENT_TYPE_GENERICINST`|제네릭 형식에 대 한 형식 한정자입니다.|  
|`ELEMENT_TYPE_TYPEDBYREF`|형식화된 참조입니다.|  
|`ELEMENT_TYPE_I`|기본 정수 크기입니다.|  
|`ELEMENT_TYPE_U`|부호 없는 원시 정수 크기입니다.|  
|`ELEMENT_TYPE_FNPTR`|함수에 대 한 포인터입니다.|  
|`ELEMENT_TYPE_OBJECT`|System.Object 형식입니다.|  
|`ELEMENT_TYPE_SZARRAY`|단일 차원, 0 인 배열 형식 한정자|  
|`ELEMENT_TYPE_MVAR`|메서드 변수 형식 한정자입니다.|  
|`ELEMENT_TYPE_CMOD_REQD`|C 언어는 필수 한정자입니다.|  
|`ELEMENT_TYPE_CMOD_OPT`|C 언어의 선택적 한정자입니다.|  
|`ELEMENT_TYPE_INTERNAL`|내부적으로 사용 합니다.|  
|`ELEMENT_TYPE_MAX`|잘못된 형식입니다.|  
|`ELEMENT_TYPE_MODIFIER`|내부적으로 사용 합니다.|  
|`ELEMENT_TYPE_SENTINEL`|형식 한정자가 가변 개수의 매개 변수 목록에 대 한 센티널입니다.|  
|`ELEMENT_TYPE_PINNED`|내부적으로 사용 합니다.|  
  
## <a name="remarks"></a>설명  
 형식 한정자는 더 복잡 한 형식을 나타내는 대 한 기초를 형성 합니다. A `CorElementType` 형식 한정자 값 바로 뒤에 오는 형식 서명에 하는 값에 적용 됩니다. 다음에 나오는 값의 `CorElementType` 형식 한정자 값이 될 수 있습니다는 `CorElementType` 단순 유형 값, 메타 데이터 토큰 또는 다음 테이블에 지정 된 다른 값입니다.  
  
> [!NOTE]
>  모든 숫자 (*번호*, *인수 개수*, *메타 데이터 토큰*, *순위*, *count*, 및 *바인딩된*) 압축 된 정수로 저장 됩니다. 참조 [Standard ecma-335-인프라 CLI (공용 언어)](http://go.microsoft.com/fwlink/?LinkID=116487) 자세한 내용은 ECMA 웹 사이트에서.  
  
|형식 한정자|형식|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR <는 `CorElementType` 값 >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF <는 `CorElementType` 값 >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE <는 `mdTypeDef` 메타 데이터 토큰 >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS <는 `mdTypeDef` 메타 데이터 토큰 >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<번호 >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY <는 `CorElementType` 값 > \<순위 > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST <는 `mdTypeDef` 메타 데이터 토큰 > \<인수 개수 > \<arg1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<호출 규칙을 포함 하는 함수에 대 한 전체 시그니처 >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY <는 `CorElementType` 값 >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<번호 >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ <는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT <는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 >|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
