---
title: "ICeeGen::TruncateSection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.TruncateSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="61720-102">ICeeGen::TruncateSection 메서드</span><span class="sxs-lookup"><span data-stu-id="61720-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="61720-103">지정 된 길이 의해 지정 된 코드 섹션을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="61720-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="61720-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61720-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61720-105">구문</span><span class="sxs-lookup"><span data-stu-id="61720-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61720-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61720-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="61720-107">[in] 파일을 자르거나 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="61720-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="61720-108">[in] Truncate 섹션을 바이트 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="61720-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61720-109">설명</span><span class="sxs-lookup"><span data-stu-id="61720-109">Remarks</span></span>  
 <span data-ttu-id="61720-110">호출 `TruncateSection` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="61720-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61720-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61720-111">Requirements</span></span>  
 <span data-ttu-id="61720-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61720-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61720-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61720-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61720-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="61720-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61720-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61720-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61720-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61720-116">See Also</span></span>  
 [<span data-ttu-id="61720-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61720-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
