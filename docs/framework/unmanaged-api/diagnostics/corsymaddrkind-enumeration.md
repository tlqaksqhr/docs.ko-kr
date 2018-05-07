---
title: CorSymAddrKind 열거형
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98cf49714829b4b2f80e0240c2ebde7fa6c280e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 열거형
메모리 주소 유형을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|가 Microsoft MSIL (intermediate language) 지역 변수 또는 매개 변수 인덱스를 나타냅니다.|  
|`ADDR_NATIVE_RVA`|모듈에 상대 가상 주소를 나타냅니다.|  
|`ADDR_NATIVE_REGISTER`|CPU 레지스터를 나타냅니다.|  
|`ADDR_NATIVE_REGREL`|첫 번째 주소는 레지스터와 두 번째 주소는 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_OFFSET`|기본 주소에서의 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_REGREG`|첫 번째 주소는 하위 부분이 있으면 레지스터의 두 번째 주소는 높은 부분을 나타냅니다.|  
|`ADDR_NATIVE_REGSTK`|첫 번째 주소는 레지스터의 하위 부분이, 두 번째는 높은 부분 및 세 번째는 오프셋을 나타냅니다.|  
|`ADDR_NATIVE_STKREG`|첫 번째 주소는 레지스터는 오프셋, 두 번째 및 세 번째는 레지스터의 많은 부분을 나타냅니다.|  
|`ADDR_BITFIELD`|첫 번째 주소는 필드의 시작 및 두 번째 주소는 필드 길이 나타냅니다.|  
|`ADDR_NATIVE_ISECTOFFSET`|첫 번째 주소 섹션은 두 번째 주소는 오프셋을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고 항목  
 [진단 기호 저장소 열거형](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
