---
title: "ICeeGen::AddSectionReloc 메서드"
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
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e4bb3b1e436f51726ce50f80e1fd88c10f20fd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="b54f6-102">ICeeGen::AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="b54f6-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="b54f6-103">코드 베이스에.reloc 명령을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="b54f6-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="b54f6-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b54f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b54f6-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b54f6-107">[in] 메모리 내 코드를 추가할.reloc 명령을 섹션.</span><span class="sxs-lookup"><span data-stu-id="b54f6-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="b54f6-108">[in] 섹션의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="b54f6-109">[in] 섹션에 있는 `offset` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="b54f6-110">[in] 중 하나는 [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) .reloc 명령 추가 하려면의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b54f6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b54f6-111">Requirements</span></span>  
 <span data-ttu-id="b54f6-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b54f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b54f6-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b54f6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b54f6-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b54f6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b54f6-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b54f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54f6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b54f6-116">See Also</span></span>  
 [<span data-ttu-id="b54f6-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b54f6-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
