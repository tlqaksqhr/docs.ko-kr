---
title: ICeeGen::GetSectionDataLen 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b85cdee4a65e91c51fdb014bdcc4797b99214daf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446133"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="0a4d3-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="0a4d3-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="0a4d3-103">지정된 된 섹션의 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="0a4d3-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4d3-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a4d3-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a4d3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a4d3-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0a4d3-107">[in] 데이터 섹션 길이가 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="0a4d3-108">[out] 지정된 된 섹션의 반환 된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a4d3-109">설명</span><span class="sxs-lookup"><span data-stu-id="0a4d3-109">Remarks</span></span>  
 <span data-ttu-id="0a4d3-110">호출 `GetSectionDataLen` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a4d3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a4d3-111">Requirements</span></span>  
 <span data-ttu-id="0a4d3-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4d3-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a4d3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a4d3-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0a4d3-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a4d3-115">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4d3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a4d3-116">See Also</span></span>  
 [<span data-ttu-id="0a4d3-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a4d3-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
