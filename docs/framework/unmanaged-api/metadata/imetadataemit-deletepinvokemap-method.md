---
title: "IMetaDataEmit::DeletePinvokeMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeletePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef79c7696f9d697d3306634635c5c00bfd1f00c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="5cf2e-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="5cf2e-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="5cf2e-103">지정한 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cf2e-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5cf2e-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cf2e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cf2e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5cf2e-106">[in] `mdFieldDef` 또는 `mdMethodDef` PInvoke 매핑 메타 데이터를 삭제 하려는 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf2e-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf2e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cf2e-107">Requirements</span></span>  
 <span data-ttu-id="5cf2e-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5cf2e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf2e-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5cf2e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cf2e-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5cf2e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cf2e-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf2e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf2e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cf2e-112">See Also</span></span>  
 [<span data-ttu-id="5cf2e-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cf2e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5cf2e-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cf2e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
