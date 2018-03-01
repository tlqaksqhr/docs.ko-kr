---
title: "IMetaDataImport::FindMember 메서드"
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
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="234ca-102">IMetaDataImport::FindMember 메서드</span><span class="sxs-lookup"><span data-stu-id="234ca-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="234ca-103">토큰을 가져옵니다 memberdef 필드 또는 메서드가 포함 된에 대 한 지정 된 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="234ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="234ca-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="234ca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="234ca-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="234ca-106">[in] 클래스 또는 검색할 멤버를 포함 하는 인터페이스에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="234ca-107">이 값이 `mdTokenNil`, 전역 변수 또는 전역 함수에 대 한 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="234ca-108">[in] 검색할 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="234ca-109">[in] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="234ca-110">[in] 바이트 크기 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="234ca-111">[out] 일치 하는 MemberDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="234ca-112">설명</span><span class="sxs-lookup"><span data-stu-id="234ca-112">Remarks</span></span>  
 <span data-ttu-id="234ca-113">바깥쪽 클래스 또는 인터페이스를 사용 하 여 멤버를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="234ca-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="234ca-114">클래스 또는 인터페이스에 이름이 같은 여러 멤버가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="234ca-115">이 경우 전달 해당 멤버의 시그니처에 고유 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="234ca-116">에 전달 된 서명을 `FindMember` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="234ca-117">서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="234ca-118">토큰은 로컬 TypeDef 테이블에 대 한 인덱스.</span><span class="sxs-lookup"><span data-stu-id="234ca-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="234ca-119">현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 입력으로 사용할 수는 없습니다 `FindMember`합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="234ca-120">`FindMember`클래스 또는 인터페이스에 직접 정의 된 구성원을 찾습니다. 상속 된 멤버는 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="234ca-121">`FindMember`도우미 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="234ca-122">호출 [imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)호출 하는 일치 하는 항목을 찾을 수 없는 경우; `FindMember` 다음 호출 [imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="234ca-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="234ca-123">Requirements</span></span>  
 <span data-ttu-id="234ca-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="234ca-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="234ca-125">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="234ca-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="234ca-126">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="234ca-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="234ca-127">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="234ca-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234ca-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="234ca-128">See Also</span></span>  
 [<span data-ttu-id="234ca-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="234ca-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="234ca-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="234ca-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
