---
title: "IMetaDataEmit::SetParent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ede8541cbf0f5d66c4d6c4ecf3bd7fee8e296038
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="e340c-102">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="e340c-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="e340c-103">설정에 대 한 이전 호출에 정의 된 대로 지정된 된 멤버를 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), 이전 호출에 정의 된 대로 지정 된 형식의 멤버는 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e340c-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e340c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e340c-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e340c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e340c-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="e340c-106">[in] `mdMemberRef` 토큰 새 부모를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e340c-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="e340c-107">[in] `mdToken` 새 부모에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e340c-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e340c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e340c-108">Requirements</span></span>  
 <span data-ttu-id="e340c-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e340c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e340c-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e340c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e340c-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e340c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e340c-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e340c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e340c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e340c-113">See Also</span></span>  
 [<span data-ttu-id="e340c-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e340c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e340c-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e340c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
