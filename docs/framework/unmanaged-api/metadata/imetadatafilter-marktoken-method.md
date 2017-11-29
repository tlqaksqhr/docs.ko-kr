---
title: "IMetaDataFilter::MarkToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter.MarkToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 608d7aa87103c5144997bfa1feb69a88b5fb1ffe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="d2b5d-102">IMetaDataFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d2b5d-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="d2b5d-103">지정한 메타 데이터 토큰이 처리 되었는지 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b5d-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2b5d-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2b5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2b5d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d2b5d-106">[in] 처리 된 것으로 표시 하려면 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b5d-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b5d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2b5d-107">Requirements</span></span>  
 <span data-ttu-id="d2b5d-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b5d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b5d-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2b5d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2b5d-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d2b5d-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2b5d-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b5d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b5d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2b5d-112">See Also</span></span>  
 [<span data-ttu-id="d2b5d-113">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2b5d-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
