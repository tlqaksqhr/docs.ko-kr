---
title: "IMetaDataImport::EnumMembers 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembers
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa7dabad0e555fe965cba4e5cbc69c10c9826b8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="c2409-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="c2409-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="c2409-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2409-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2409-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2409-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2409-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c2409-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c2409-107">[in] 열거할를 구성원으로 포함 된 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="c2409-108">[out] MemberDef 토큰을 보유 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c2409-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c2409-110">[out] 반환 된 MemberDef 토큰의 실제 수 `rMembers`합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2409-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c2409-111">Return Value</span></span>  
  
|<span data-ttu-id="c2409-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2409-112">HRESULT</span></span>|<span data-ttu-id="c2409-113">설명</span><span class="sxs-lookup"><span data-stu-id="c2409-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c2409-114">`EnumMembers`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c2409-115">열거할 MemberDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="c2409-116">이 경우 `pcTokens` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2409-117">설명</span><span class="sxs-lookup"><span data-stu-id="c2409-117">Remarks</span></span>  
 <span data-ttu-id="c2409-118">클래스에 대 한 멤버의 컬렉션을 열거 하는 경우 `EnumMembers` 클래스에서 직접 정의 된 멤버만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="c2409-119">해당 클래스가 상속 하는 멤버는 클래스는 상속 된 멤버에 대 한 구현을 제공 하는 경우에 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="c2409-120">상속 된 멤버를 열거 하려면 호출자에 게 상속 체인을 명시적으로 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="c2409-121">상속 체인에 대 한 규칙 언어 또는 발생 하면 원래의 메타 데이터는 컴파일러에 따라 다를 수 있습니다는 참고 사항</span><span class="sxs-lookup"><span data-stu-id="c2409-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2409-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2409-122">Requirements</span></span>  
 <span data-ttu-id="c2409-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2409-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2409-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2409-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2409-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c2409-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2409-126">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2409-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2409-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2409-127">See Also</span></span>  
 [<span data-ttu-id="c2409-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2409-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c2409-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2409-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
