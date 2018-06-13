---
title: CorNativeType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b28fe8e8fd8b602a01b6358f46f60cdf792ced0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448627"
---
# <a name="cornativetype-enumeration"></a>CorNativeType 열거형
관리되지 않는 네이티브 형식을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|사용되지 않습니다.|  
|`NATIVE_TYPE_VOID`|사용되지 않습니다.|  
|`NATIVE_TYPE_BOOLEAN`|여기서 TRUE는 0이 아닌 및 FALSE는 4 바이트 부울 값은 0입니다.|  
|`NATIVE_TYPE_I1`|부호 있는 8 비트 정수 값입니다.|  
|`NATIVE_TYPE_U1`|부호 없는 8 비트 정수 값입니다.|  
|`NATIVE_TYPE_I2`|부호 있는 16 비트 정수 값입니다.|  
|`NATIVE_TYPE_U2`|부호 없는 16 비트 정수 값입니다.|  
|`NATIVE_TYPE_I4`|부호 있는 32비트 정수 값입니다.|  
|`NATIVE_TYPE_U4`|부호 없는 32비트 정수 값입니다.|  
|`NATIVE_TYPE_I8`|부호 있는 64 비트 정수 값입니다.|  
|`NATIVE_TYPE_U8`|부호 없는 64 비트 정수 값입니다.|  
|`NATIVE_TYPE_R4`|4 바이트 부동 소수점 숫자 값입니다.|  
|`NATIVE_TYPE_R8`|8 바이트 부동 소수점 숫자 값입니다.|  
|`NATIVE_TYPE_SYSCHAR`|사용되지 않습니다.|  
|`NATIVE_TYPE_VARIANT`|사용되지 않습니다.|  
|`NATIVE_TYPE_CURRENCY`|관리 되는 것에 해당 하는 숫자 COM 형식을 <xref:System.Decimal> 유형입니다.|  
|`NATIVE_TYPE_PTR`|사용되지 않습니다.|  
|`NATIVE_TYPE_DECIMAL`|사용되지 않습니다.|  
|`NATIVE_TYPE_DATE`|사용되지 않습니다.|  
|`NATIVE_TYPE_BSTR`|COM Interop 합니다.|  
|`NATIVE_TYPE_LPSTR`|LPSTR 문자열 값입니다.|  
|`NATIVE_TYPE_LPWSTR`|LPWSTR 문자열 값입니다.|  
|`NATIVE_TYPE_LPTSTR`|LPTSTR 문자열 값입니다.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|고정, 시스템에 정의 된 문자열 값입니다.|  
|`NATIVE_TYPE_OBJECTREF`|사용되지 않습니다.|  
|`NATIVE_TYPE_IUNKNOWN`|COM Interop 합니다.|  
|`NATIVE_TYPE_IDISPATCH`|COM Interop 합니다.|  
|`NATIVE_TYPE_STRUCT`|네이티브 구조체 값입니다.|  
|`NATIVE_TYPE_INTF`|COM Interop 합니다.|  
|`NATIVE_TYPE_SAFEARRAY`|COM Interop 합니다.|  
|`NATIVE_TYPE_FIXEDARRAY`|고정 길이의 배열 값입니다.|  
|`NATIVE_TYPE_INT`|네이티브 16 비트 부호 있는 정수 값입니다.|  
|`NATIVE_TYPE_UINT`|기본 16 비트 부호 없는 정수 값입니다.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|사용되지 않습니다.<br /><br /> NATIVE_TYPE_STRUCT를 사용 합니다.|  
|`NATIVE_TYPE_BYVALSTR`|COM Interop 합니다.|  
|`NATIVE_TYPE_ANSIBSTR`|COM Interop 합니다.|  
|`NATIVE_TYPE_TBSTR`|COM Interop 합니다.<br /><br /> BSTR 또는 ANSIBSTR 플랫폼에 따라 선택 합니다.|  
|`NATIVE_TYPE_VARIANTBOOL`|2 바이트 부울 값, 여기서 TRUE은-1이 고 FALSE는 0입니다.|  
|`NATIVE_TYPE_FUNC`|함수 포인터입니다.|  
|`NATIVE_TYPE_ASANY`|네이티브 형식에 대 한 참조입니다.|  
|`NATIVE_TYPE_ARRAY`|알 수 없는 형식의 멤버가 포함 된 배열에 대 한 참조입니다.|  
|`NATIVE_TYPE_LPSTRUCT`|구조에 대 한 32 비트 정수 포인터입니다.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|사용자 지정 마샬러 네이티브 형식입니다.<br /><br /> 이 뒤에 다음과 같은 형식의 문자열로 야: "네이티브 형식 이름/0 사용자 지정 마샬러는 이름/0 선택적 쿠키/0 형식" 또는 "{네이티브 입력 GUID} 0 사용자 지정 마샬러 형식 이름/0 선택적 쿠키/0 /"|  
|`NATIVE_TYPE_ERROR`|COM Interop 합니다.<br /><br /> ELEMENT_TYPE_I4 사용이 형식은 VT_HRESULT에 매핑됩니다.|  
|`NATIVE_TYPE_IINSPECTABLE`|네이티브 `IInspectable` 유형입니다.|  
|`NATIVE_TYPE_HSTRING`|네이티브 `HString`합니다.|  
|`NATIVE_TYPE_MAX`|잘못 된 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.UnmanagedType>  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
