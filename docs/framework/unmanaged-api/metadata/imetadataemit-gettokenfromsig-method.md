---
title: "IMetaDataEmit::GetTokenFromSig 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetTokenFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aefd95f62fce70f87c0724cbb4013462a449c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="971cd-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="971cd-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="971cd-103">지정한 메타 데이터 서명에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="971cd-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="971cd-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="971cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="971cd-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="971cd-106">[in] 서명 유지 하 고 저장입니다.</span><span class="sxs-lookup"><span data-stu-id="971cd-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="971cd-107">[in] 바이트 수 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="971cd-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="971cd-108">[out] `mdSignature` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="971cd-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="971cd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="971cd-109">Requirements</span></span>  
 <span data-ttu-id="971cd-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="971cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="971cd-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="971cd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="971cd-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="971cd-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="971cd-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="971cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971cd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="971cd-114">See Also</span></span>  
 [<span data-ttu-id="971cd-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="971cd-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="971cd-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="971cd-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
