---
title: "IMetaDataEmit::DefineMethodImpl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5bf16c51a241a01f18aae84f8b3bb7554f08b87c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="32ea9-102">IMetaDataEmit::DefineMethodImpl 메서드</span><span class="sxs-lookup"><span data-stu-id="32ea9-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="32ea9-103">인터페이스에서 상속 된 메서드의 구현에 대 한 정의 만들고 해당 메서드 구현 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ea9-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32ea9-104">구문</span><span class="sxs-lookup"><span data-stu-id="32ea9-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32ea9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32ea9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="32ea9-106">[in] `mdTypedef` 토큰 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="32ea9-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="32ea9-107">[in] `mdMethodDef` 또는 `mdMethodRef` 코드 본문의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="32ea9-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="32ea9-108">[in] `mdMethodDef` 또는 `mdMethodRef` 구현 되는 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="32ea9-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32ea9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32ea9-109">Requirements</span></span>  
 <span data-ttu-id="32ea9-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32ea9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32ea9-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32ea9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32ea9-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="32ea9-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32ea9-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32ea9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ea9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32ea9-114">See Also</span></span>  
 [<span data-ttu-id="32ea9-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32ea9-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="32ea9-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32ea9-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
