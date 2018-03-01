---
title: "IMetaDataImport::EnumTypeRefs 메서드"
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
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3099f129abd3477aeb08526b9f0dcd5b701d4dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="2f3cf-102">IMetaDataImport::EnumTypeRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="2f3cf-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="2f3cf-103">현재 메타데이터 범위에서 정의된 TypeRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f3cf-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f3cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f3cf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2f3cf-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2f3cf-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="2f3cf-108">[out] TypeRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2f3cf-109">[in] `rTypeRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="2f3cf-110">[out] 반환 된 TypeRef 토큰의 수에 대 한 포인터 `rTypeRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f3cf-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="2f3cf-111">Return Value</span></span>  
  
|<span data-ttu-id="2f3cf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f3cf-112">HRESULT</span></span>|<span data-ttu-id="2f3cf-113">설명</span><span class="sxs-lookup"><span data-stu-id="2f3cf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2f3cf-114">`EnumTypeRefs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2f3cf-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2f3cf-116">이 경우 `pcTypeRefs` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3cf-117">설명</span><span class="sxs-lookup"><span data-stu-id="2f3cf-117">Remarks</span></span>  
 <span data-ttu-id="2f3cf-118">TypeRef 토큰 형식에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3cf-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f3cf-119">Requirements</span></span>  
 <span data-ttu-id="2f3cf-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3cf-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f3cf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f3cf-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2f3cf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f3cf-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f3cf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3cf-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f3cf-124">See Also</span></span>  
 [<span data-ttu-id="2f3cf-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3cf-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2f3cf-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f3cf-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
