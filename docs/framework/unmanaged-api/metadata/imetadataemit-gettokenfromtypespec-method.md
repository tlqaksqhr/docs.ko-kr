---
title: "IMetaDataEmit::GetTokenFromTypeSpec 메서드"
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
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6acb9d340aa1dc8df5d0b9dc3b0c0dd9c159257e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="945f7-102">IMetaDataEmit::GetTokenFromTypeSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="945f7-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="945f7-103">지정한 메타 데이터 서명 사용 하 여 형식에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="945f7-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="945f7-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="945f7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="945f7-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="945f7-106">[in] 정의 하 고 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="945f7-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="945f7-107">[in] 바이트 수 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="945f7-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="945f7-108">[out] `mdTypeSpec` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="945f7-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="945f7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="945f7-109">Requirements</span></span>  
 <span data-ttu-id="945f7-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="945f7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="945f7-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="945f7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="945f7-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="945f7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="945f7-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="945f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945f7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="945f7-114">See Also</span></span>  
 [<span data-ttu-id="945f7-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945f7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="945f7-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="945f7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
