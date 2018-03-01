---
title: "IMetaDataEmit::DefineCustomAttribute 메서드"
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
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 053601376f8b75e5469a3ef8a3d890a6c6620e28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="47587-102">IMetaDataEmit::DefineCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="47587-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="47587-103">지정한 메타 데이터 서명이 지정된 된 개체에 연결 될 사용 하 여 사용자 지정 특성에 대 한 정의 만들고 해당 사용자 지정 특성 정의 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47587-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47587-104">구문</span><span class="sxs-lookup"><span data-stu-id="47587-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47587-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47587-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="47587-106">[in] 소유자 항목에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="47587-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="47587-107">[in] 사용자 지정 특성을 식별 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="47587-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="47587-108">[in] 사용자 지정 특성에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="47587-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="47587-109">[in] 바이트 수 `pCustomAttribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="47587-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="47587-110">[out] `mdCustomAttribute` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="47587-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47587-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47587-111">Requirements</span></span>  
 <span data-ttu-id="47587-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47587-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47587-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47587-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47587-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="47587-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47587-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47587-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47587-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47587-116">See Also</span></span>  
 [<span data-ttu-id="47587-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47587-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="47587-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47587-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
