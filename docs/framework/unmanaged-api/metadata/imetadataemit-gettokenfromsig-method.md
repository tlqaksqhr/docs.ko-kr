---
title: IMetaDataEmit::GetTokenFromSig 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be42fea034be4fe5d48874b00db86977a3039a34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448222"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="d0461-102">IMetaDataEmit::GetTokenFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="d0461-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="d0461-103">지정한 메타 데이터 서명에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0461-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0461-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0461-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0461-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0461-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="d0461-106">[in] 서명 유지 하 고 저장입니다.</span><span class="sxs-lookup"><span data-stu-id="d0461-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="d0461-107">[in] 바이트 수 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0461-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="d0461-108">[out] `mdSignature` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d0461-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0461-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0461-109">Requirements</span></span>  
 <span data-ttu-id="d0461-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0461-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0461-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0461-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0461-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d0461-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0461-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0461-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0461-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0461-114">See Also</span></span>  
 [<span data-ttu-id="d0461-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0461-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d0461-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0461-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
