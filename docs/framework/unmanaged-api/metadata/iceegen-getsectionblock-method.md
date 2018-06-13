---
title: ICeeGen::GetSectionBlock 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5da2936a46dcf3d8f69acc3367db64712165b0cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444069"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="af61a-102">ICeeGen::GetSectionBlock 메서드</span><span class="sxs-lookup"><span data-stu-id="af61a-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="af61a-103">코드 베이스의 섹션 블록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="af61a-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af61a-105">구문</span><span class="sxs-lookup"><span data-stu-id="af61a-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="af61a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af61a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="af61a-107">[in] 코드 베이스의 블록 검색 하려는 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="af61a-108">[in] 검색할 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="af61a-109">[in] 블록의 첫 번째 바이트를 정렬 하는 데 사용할 섹션의 시작을 기준으로 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="af61a-110">이 섹션 내에서 블록의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="af61a-111">[out] 검색 된 블록의 주소를 받는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af61a-112">설명</span><span class="sxs-lookup"><span data-stu-id="af61a-112">Remarks</span></span>  
 <span data-ttu-id="af61a-113">호출 `GetSectionBlock` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af61a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af61a-114">Requirements</span></span>  
 <span data-ttu-id="af61a-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af61a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af61a-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af61a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af61a-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="af61a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af61a-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af61a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af61a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af61a-119">See Also</span></span>  
 [<span data-ttu-id="af61a-120">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af61a-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
