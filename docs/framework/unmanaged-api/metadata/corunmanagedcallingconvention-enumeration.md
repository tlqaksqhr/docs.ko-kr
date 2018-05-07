---
title: CorUnmanagedCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention 열거형
비관리 코드에 대 한 호출 규칙을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|C 언어 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|표준 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|"This" 호출 규칙입니다.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|"빠른" 호출 규칙입니다.|  
|`IMAGE_CEE_CS_CALLCONV_C`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|사용되지 않습니다.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|사용되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 CLR은.NET Framework 버전 1.0에서에서 "고속" 호출 규칙을 지원 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
