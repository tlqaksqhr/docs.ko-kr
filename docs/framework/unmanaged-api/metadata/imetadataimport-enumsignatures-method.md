---
title: "IMetaDataImport::EnumSignatures 메서드"
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
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 88d47e2512103947f007c81450157a0b3e334a33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="16f2c-102">IMetaDataImport::EnumSignatures 메서드</span><span class="sxs-lookup"><span data-stu-id="16f2c-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="16f2c-103">현재 범위의 독립 실행형 서명을 나타내는 Signature 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="16f2c-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16f2c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16f2c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="16f2c-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="16f2c-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="16f2c-108">[out] 서명 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="16f2c-109">[in] `rSignatures` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="16f2c-110">[out] 반환 된 서명 토큰 수 `rSignatures`합니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16f2c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="16f2c-111">Return Value</span></span>  
  
|<span data-ttu-id="16f2c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16f2c-112">HRESULT</span></span>|<span data-ttu-id="16f2c-113">설명</span><span class="sxs-lookup"><span data-stu-id="16f2c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="16f2c-114">`EnumSignatures`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="16f2c-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="16f2c-116">이 경우 `pcSignatures` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16f2c-117">설명</span><span class="sxs-lookup"><span data-stu-id="16f2c-117">Remarks</span></span>  
 <span data-ttu-id="16f2c-118">서명 토큰에 의해 만들어집니다는 [imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="16f2c-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16f2c-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16f2c-119">Requirements</span></span>  
 <span data-ttu-id="16f2c-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16f2c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16f2c-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="16f2c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16f2c-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="16f2c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16f2c-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16f2c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f2c-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f2c-124">See Also</span></span>  
 [<span data-ttu-id="16f2c-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16f2c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="16f2c-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16f2c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
