---
title: "ICeeGen::GetSectionCreate 메서드"
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
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a069f65d3059bfa427ea20623ff9a2ac4049fd39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="97f15-102">ICeeGen::GetSectionCreate 메서드</span><span class="sxs-lookup"><span data-stu-id="97f15-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="97f15-103">생성 하 고 지정한 이름 및 플래그 값을 사용 하는 코드 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="97f15-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f15-105">구문</span><span class="sxs-lookup"><span data-stu-id="97f15-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97f15-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97f15-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="97f15-107">[in] 만들 섹션의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="97f15-108">[in] 옵션을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="97f15-109">[out] 새로 생성된 된 코드 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f15-110">설명</span><span class="sxs-lookup"><span data-stu-id="97f15-110">Remarks</span></span>  
 <span data-ttu-id="97f15-111">호출 `GetSectionCreate` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f15-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97f15-112">Requirements</span></span>  
 <span data-ttu-id="97f15-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97f15-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f15-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="97f15-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97f15-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="97f15-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97f15-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f15-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f15-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97f15-117">See Also</span></span>  
 [<span data-ttu-id="97f15-118">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97f15-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
