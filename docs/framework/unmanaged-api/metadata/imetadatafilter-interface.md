---
title: "IMetaDataFilter 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7c0afbb9be9af3ffe69ddfcac85b70de53a391ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="5545f-102">IMetaDataFilter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5545f-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="5545f-103">이미 수행된 반복 작업을 방지하려고 메타데이터 토큰을 표시 및 필터링하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5545f-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5545f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5545f-104">Methods</span></span>  
  
|<span data-ttu-id="5545f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5545f-105">Method</span></span>|<span data-ttu-id="5545f-106">설명</span><span class="sxs-lookup"><span data-stu-id="5545f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5545f-107">IsTokenMarked 메서드</span><span class="sxs-lookup"><span data-stu-id="5545f-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="5545f-108">지정한 메타 데이터 토큰 처리 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5545f-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="5545f-109">MarkToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5545f-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="5545f-110">지정한 메타 데이터 토큰이 처리 되었는지 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5545f-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="5545f-111">UnmarkAll 메서드</span><span class="sxs-lookup"><span data-stu-id="5545f-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="5545f-112">현재 메타 데이터 범위에서 모든 토큰에서 처리 표시를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5545f-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5545f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5545f-113">Requirements</span></span>  
 <span data-ttu-id="5545f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5545f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5545f-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5545f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5545f-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5545f-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5545f-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5545f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5545f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5545f-118">See Also</span></span>  
 [<span data-ttu-id="5545f-119">메타 데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5545f-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
