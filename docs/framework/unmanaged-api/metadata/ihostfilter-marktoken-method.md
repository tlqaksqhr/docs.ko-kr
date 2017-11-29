---
title: "IHostFilter::MarkToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostFilter.MarkToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9556880ad534f5c82d8d0e874129876478e2e63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="de71a-102">IHostFilter::MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="de71a-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="de71a-103">지정한 메타 데이터 토큰이 처리할지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de71a-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de71a-104">구문</span><span class="sxs-lookup"><span data-stu-id="de71a-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de71a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de71a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="de71a-106">[in] 처리할 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="de71a-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de71a-107">설명</span><span class="sxs-lookup"><span data-stu-id="de71a-107">Remarks</span></span>  
 <span data-ttu-id="de71a-108">일반적으로 원하는 메타 데이터 범위에 있으면 처리 해야 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="de71a-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="de71a-109">`MarkToken` 메서드를 통해 메타 데이터 엔진에 전달 되는 [imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="de71a-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de71a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de71a-110">Requirements</span></span>  
 <span data-ttu-id="de71a-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de71a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de71a-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de71a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de71a-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="de71a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de71a-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de71a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de71a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de71a-115">See Also</span></span>  
 [<span data-ttu-id="de71a-116">메타 데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de71a-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="de71a-117">IHostFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de71a-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
