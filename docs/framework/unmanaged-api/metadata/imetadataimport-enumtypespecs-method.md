---
title: "IMetaDataImport::EnumTypeSpecs 메서드"
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
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e34a3086474918c913a366c02bbf9eadf313b43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="758a9-102">IMetaDataImport::EnumTypeSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="758a9-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="758a9-103">현재 메타데이터 범위에서 정의된 TypeSpec 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="758a9-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="758a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="758a9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="758a9-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="758a9-107">이 값이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="758a9-108">[out] TypeSpec 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="758a9-109">[in] `rTypeSpecs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="758a9-110">[out] 반환 된 TypeSpec 토큰 수 `rTypeSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="758a9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="758a9-111">Return Value</span></span>  
  
|<span data-ttu-id="758a9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="758a9-112">HRESULT</span></span>|<span data-ttu-id="758a9-113">설명</span><span class="sxs-lookup"><span data-stu-id="758a9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="758a9-114">`EnumTypeSpecs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="758a9-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="758a9-116">이 경우 `pcTypeSpecs` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="758a9-117">설명</span><span class="sxs-lookup"><span data-stu-id="758a9-117">Remarks</span></span>  
 <span data-ttu-id="758a9-118">TypeSpec 토큰에 의해 만들어집니다는 [imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="758a9-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="758a9-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="758a9-119">Requirements</span></span>  
 <span data-ttu-id="758a9-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="758a9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="758a9-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="758a9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="758a9-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="758a9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="758a9-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="758a9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758a9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="758a9-124">See Also</span></span>  
 [<span data-ttu-id="758a9-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="758a9-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="758a9-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="758a9-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
