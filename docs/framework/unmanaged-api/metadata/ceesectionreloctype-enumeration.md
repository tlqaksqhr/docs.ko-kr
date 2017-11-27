---
title: "CeeSectionRelocType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocType
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocType
helpviewer_keywords: CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d78b6b3867cb168e4ebf93c07f17a911e1955832
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="c74f8-102">CeeSectionRelocType 열거형</span><span class="sxs-lookup"><span data-stu-id="c74f8-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="c74f8-103">값의 형식에 영향을을 제공 `reloc` 명령에 대 한 호출에 포함 된 [iceegen:: Addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c74f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="c74f8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c74f8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c74f8-105">Members</span></span>  
  
|<span data-ttu-id="c74f8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c74f8-106">Member</span></span>|<span data-ttu-id="c74f8-107">설명</span><span class="sxs-lookup"><span data-stu-id="c74f8-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="c74f8-108">섹션 관련만 생성 `reloc`.reloc 섹션에 아무 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="c74f8-109">생성 한 `reloc` 포인터 크기의 위치에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="c74f8-110">플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="c74f8-111">생성 한 `reloc` 상위 16 비트의 32 비트 숫자에서는 하위 16 비트에에서 다음 단어에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="c74f8-112">아무 것도.reloc 섹션으로 보내는 토큰 맵을 재배치를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="c74f8-113">값이 상대 주소 픽스업 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="c74f8-114">섹션 관련만 생성 `reloc`.reloc 섹션에 아무 것도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="c74f8-115">이 `reloc` 섹션의 가상 주소가 아니라 섹션의 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="c74f8-116">픽스업 코드 상대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="c74f8-117">생성 된 `reloc` ia64에서 64 비트 주소에 대 한 `movl` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="c74f8-118">생성 한 `reloc` 64 비트 주소에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="c74f8-119">생성 된 `reloc` ia64에서 25-비트 PC 상대 주소에 대 한 `br.call` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="c74f8-120">생성 된 `reloc` 에 ia64 64 비트 PC 상대 주소에 대 한 `brl.call` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="c74f8-121">에서는 30 비트 섹션 관련 오류가 발생 하는 경우 `reloc`태그가 지정 된 포인터 값에,를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="c74f8-122">이 열거형에 대 한 추가 되도록 센티널 값 내부에 반영 됩니다 `reloc` 이름 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="c74f8-123">기본 방출 하지 않도록 지정 `reloc`합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="c74f8-124">픽스업 전의 메모리 내용이 섹션 아니라 포인터를 나타내는 값을 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c74f8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c74f8-125">Requirements</span></span>  
 <span data-ttu-id="c74f8-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c74f8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c74f8-127">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c74f8-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c74f8-128">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c74f8-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c74f8-129">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c74f8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c74f8-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c74f8-130">See Also</span></span>  
 [<span data-ttu-id="c74f8-131">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c74f8-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="c74f8-132">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c74f8-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [<span data-ttu-id="c74f8-133">AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="c74f8-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
