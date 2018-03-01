---
title: "IMetaDataImport::EnumMembersWithName 메서드"
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
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b0cef8fca7be315185ab521464b251f2a94f3b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="0fbb6-102">IMetaDataImport::EnumMembersWithName 메서드</span><span class="sxs-lookup"><span data-stu-id="0fbb6-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="0fbb6-103">지정한 이름을 가진 지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fbb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fbb6-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fbb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0fbb6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0fbb6-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="0fbb6-107">[in] 열거 하는 멤버가 포함 된 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="0fbb6-108">[in] 열거자의 범위를 제한 하는 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="0fbb6-109">[out] MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0fbb6-110">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0fbb6-111">[out] 반환 된 MemberDef 토큰의 실제 수 `rMembers`합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fbb6-112">설명</span><span class="sxs-lookup"><span data-stu-id="0fbb6-112">Remarks</span></span>  
 <span data-ttu-id="0fbb6-113">이 메서드는 필드 및 메서드 하지만 하지 속성 또는 이벤트를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="0fbb6-114">와 달리 [imetadataimport:: Enummembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` 지정 된 이름이 없는 모든 필드와 멤버 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fbb6-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="0fbb6-115">Return Value</span></span>  
  
|<span data-ttu-id="0fbb6-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fbb6-116">HRESULT</span></span>|<span data-ttu-id="0fbb6-117">설명</span><span class="sxs-lookup"><span data-stu-id="0fbb6-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0fbb6-118">`EnumTypeDefs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0fbb6-119">열거할 MemberDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="0fbb6-120">이 경우 `pcTokens` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fbb6-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fbb6-121">Requirements</span></span>  
 <span data-ttu-id="0fbb6-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbb6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fbb6-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0fbb6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fbb6-124">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0fbb6-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fbb6-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fbb6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fbb6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fbb6-126">See Also</span></span>  
 [<span data-ttu-id="0fbb6-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fbb6-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0fbb6-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fbb6-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
