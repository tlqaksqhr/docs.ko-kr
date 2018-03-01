---
title: "IMetaDataImport::FindMemberRef 메서드"
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
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a94fb09e1ff62abac9dd716257ba75542453707e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="fee99-102">IMetaDataImport::FindMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="fee99-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="fee99-103">지정 된로 묶인 멤버에 대 한 MemberRef 토큰에 대 한 포인터 참조 즉 가져옵니다 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fee99-104">구문</span><span class="sxs-lookup"><span data-stu-id="fee99-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fee99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fee99-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="fee99-106">[in] 해당 클래스 또는 인터페이스에 대 한 검색에 대 한 멤버 참조를 포함 하는 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="fee99-107">이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수 참조에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="fee99-108">[in] 검색할 멤버 참조의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="fee99-109">[in] 멤버 참조가의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fee99-110">[in] 바이트 크기 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="fee99-111">[out] 일치 하는 MemberRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fee99-112">설명</span><span class="sxs-lookup"><span data-stu-id="fee99-112">Remarks</span></span>  
 <span data-ttu-id="fee99-113">바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="fee99-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="fee99-114">에 전달 된 서명을 `FindMemberRef` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="fee99-115">서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="fee99-116">토큰은 로컬 TypeDef 테이블에 대 한 인덱스.</span><span class="sxs-lookup"><span data-stu-id="fee99-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="fee99-117">현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 대 한 입력으로 사용할 수는 없습니다 `FindMemberRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="fee99-118">`FindMemberRef`클래스 또는 인터페이스에 직접 정의 된 멤버 참조를 찾습니다. 상속 된 멤버 참조는 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fee99-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fee99-119">Requirements</span></span>  
 <span data-ttu-id="fee99-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fee99-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fee99-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fee99-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fee99-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fee99-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fee99-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee99-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee99-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fee99-124">See Also</span></span>  
 [<span data-ttu-id="fee99-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fee99-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fee99-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fee99-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
