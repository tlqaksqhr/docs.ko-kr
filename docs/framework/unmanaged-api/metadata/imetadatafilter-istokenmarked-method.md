---
title: "IMetaDataFilter::IsTokenMarked 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter.IsTokenMarked
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 832f1e57e55245a84d093a41c627613d5fbe6902
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="89e48-102">IMetaDataFilter::IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="89e48-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="89e48-103">지정한 메타 데이터 토큰 처리 되었다고 표시 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89e48-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e48-104">구문</span><span class="sxs-lookup"><span data-stu-id="89e48-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89e48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89e48-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="89e48-106">[in] 처리 표시를 검사 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="89e48-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="89e48-107">[out] 값을 `true` 경우 `tk` 처리 받지 않았으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="89e48-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e48-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89e48-108">Requirements</span></span>  
 <span data-ttu-id="89e48-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89e48-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e48-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89e48-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89e48-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="89e48-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89e48-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e48-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e48-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89e48-113">See Also</span></span>  
 [<span data-ttu-id="89e48-114">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89e48-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
