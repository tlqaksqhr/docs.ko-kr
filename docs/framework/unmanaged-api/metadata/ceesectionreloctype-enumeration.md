---
title: "CeeSectionRelocType 열거형"
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
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d257778a9a05e2654d7f91c0205424d001f5ae3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 열거형
값의 형식에 영향을을 제공 `reloc` 명령에 대 한 호출에 포함 된 [iceegen:: Addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`srRelocAbsolute`|섹션 관련만 생성 `reloc`.reloc 섹션에 아무 것도 있습니다.|  
|`srRelocHighLow`|생성 한 `reloc` 포인터 크기의 위치에 대 한 합니다. 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64로 변환 됩니다.|  
|`srRelocHighAdj`|생성 한 `reloc` 상위 16 비트의 32 비트 숫자에서는 하위 16 비트에에서 다음 단어에 포함 됩니다.|  
|`srRelocMapToken`|아무 것도.reloc 섹션으로 보내는 토큰 맵을 재배치를 생성 합니다.|  
|`srRelocRelative`|값이 상대 주소 픽스업 임을 나타냅니다.|  
|`srRelocFilePos`|섹션 관련만 생성 `reloc`.reloc 섹션에 아무 것도 있습니다. 이 `reloc` 섹션의 가상 주소가 아니라 섹션의 파일 위치에 상대적입니다.|  
|`srRelocCodeRelative`|픽스업 코드 상대 주소를 지정합니다.|  
|`srRelocIA64Imm64`|생성 된 `reloc` ia64에서 64 비트 주소에 대 한 `movl` 명령입니다.|  
|`srRelocDir64`|생성 한 `reloc` 64 비트 주소에 대 한 합니다.|  
|`srRelocIA64PcRel25`|생성 된 `reloc` ia64에서 25-비트 PC 상대 주소에 대 한 `br.call` 명령입니다.|  
|`srRelocIA64PcRel64`|생성 된 `reloc` 에 ia64 64 비트 PC 상대 주소에 대 한 `brl.call` 명령입니다.|  
|`srRelocAbsoluteTagged`|에서는 30 비트 섹션 관련 오류가 발생 하는 경우 `reloc`태그가 지정 된 포인터 값에,를 사용 합니다.|  
|`srRelocSentinel`|이 열거형에 대 한 추가 되도록 센티널 값 내부에 반영 됩니다 `reloc` 이름 배열입니다.|  
|`srNoBaseReloc`|기본 방출 하지 않도록 지정 `reloc`합니다.|  
|`srRelocPtr`|픽스업 전의 메모리 내용이 섹션 아니라 포인터를 나타내는 값을 오프셋 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
