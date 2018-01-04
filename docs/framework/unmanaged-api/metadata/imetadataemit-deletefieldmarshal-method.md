---
title: "IMetaDataEmit::DeleteFieldMarshal 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce60aace95f4da8c021026cf9bfc6c195de5b05f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="37651-102">IMetaDataEmit::DeleteFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="37651-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="37651-103">지정한 토큰이 참조 하는 개체에 대 한 메타 데이터 서명을 마샬링 PInvoke를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="37651-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37651-104">구문</span><span class="sxs-lookup"><span data-stu-id="37651-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37651-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37651-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="37651-106">[in] `mdFieldDef` 또는 `mdParamDef` 필드 또는 매개 변수를 마샬링 메타 데이터 서명을 삭제할 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="37651-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37651-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37651-107">Requirements</span></span>  
 <span data-ttu-id="37651-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="37651-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37651-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37651-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37651-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="37651-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37651-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37651-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37651-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37651-112">See Also</span></span>  
 [<span data-ttu-id="37651-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37651-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="37651-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37651-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
