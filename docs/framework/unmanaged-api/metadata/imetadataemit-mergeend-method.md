---
title: "IMetaDataEmit::MergeEnd 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.MergeEnd
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 265fc007b5817e8dffd5846738a7a0003bbddf9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="0ee18-102">IMetaDataEmit::MergeEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee18-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="0ee18-103">하나 이상의 이전 호출에 의해 지정 된 모든 메타 데이터 범위를 범위에 현재 병합 [트리거합니다](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee18-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ee18-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ee18-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ee18-105">Parameters</span></span>  
 <span data-ttu-id="0ee18-106">이 메서드는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee18-107">설명</span><span class="sxs-lookup"><span data-stu-id="0ee18-107">Remarks</span></span>  
 <span data-ttu-id="0ee18-108">이 루틴은 메타 데이터의 실제 병합 트리거, 모든 범위에 대 한 호출 하 여 지정 된 가져오기 `IMetaDataEmit::Merge`, 현재 출력 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="0ee18-109">병합에는 다음과 같은 특별 한 조건이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-109">The following special conditions apply to the merge:</span></span>  
  
-   <span data-ttu-id="0ee18-110">(MVID) 모듈 버전 식별자가 하므로 가져올 수 없습니다는 메타 데이터 가져오기 범위에 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
-   <span data-ttu-id="0ee18-111">기존 없음 모듈 수준 속성을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="0ee18-112">현재 범위에 대 한 모듈 속성 이미 설정 된 경우 모듈 속성이 내보내게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="0ee18-113">그러나 현재 범위에서를 모듈 속성을 설정 하지 않은 경우 파일은 가져올 처음 발생 하면 한 번만.</span><span class="sxs-lookup"><span data-stu-id="0ee18-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="0ee18-114">이러한 모듈 속성 다시 발생 하면 중복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="0ee18-115">(제외 MVID) 모든 모듈 속성의 값이 비교 되는 경우 중복 되는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
-   <span data-ttu-id="0ee18-116">형식 정의 (`TypeDef`), 중복 행은 현재 범위에 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="0ee18-117">`TypeDef`개체를 각각에 대해 중복 검사 *정규화 된 개체 이름* + *GUID* + *버전 번호*합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="0ee18-118">이름이 나 GUID, 일치 하는 경우 다른 두 요소 중 하나라도 다른 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="0ee18-119">그렇지 않으면 일치 하는 모든 세 항목이 `MergeEnd` 한 간단한 검사 항목은 중복 항목이 실제로를 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="0ee18-120">이 한 간단한 검사가 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-120">This cursory check looks for:</span></span>  
  
    -   <span data-ttu-id="0ee18-121">동일한 멤버 선언 순서 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="0ee18-122">으로 플래그가 지정 된 멤버 `mdPrivateScope` (참조는 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형)이이 확인에 포함 되지 않은 특수 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    -   <span data-ttu-id="0ee18-123">동일한 클래스 레이아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-123">The same class layout.</span></span>  
  
     <span data-ttu-id="0ee18-124">즉, 한 `TypeDef` 개체 항상 완벽 하 게 하 고 일관 되 게를 정의 해야 모든 메타 데이터 범위에서는 자신이 선언 된; (클래스)에 대 한 해당 멤버 구현이 여러 컴파일 단위에 분산 되어 전체 정의로 간주 됩니다 모든 범위에 및 각 범위에 증분 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="0ee18-125">예를 들어 매개 변수 이름은 계약과 관련 인 내보내야 동일한 방식으로 모든 범위;에 관련이 없는 경우 이러한 내보내지 않아야 메타 데이터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="0ee18-126">`TypeDef` 증분 멤버로 플래그가 지정 된 개체에 있을 수 `mdPrivateScope`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="0ee18-127">이러한, `MergeEnd` 증분 중복 관계 없이 현재 범위에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="0ee18-128">컴파일러에서 개인 범위를 식별 하기 때문에 컴파일러 규칙 적용을 담당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
-   <span data-ttu-id="0ee18-129">(Rva) 상대 가상 주소 가져오거나 병합; 컴파일러는이 정보를 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
-   <span data-ttu-id="0ee18-130">사용자 지정 특성이 연결 되어 있는 항목이 병합 될 때에 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="0ee18-131">예를 들어 클래스와 연관 된 사용자 지정 특성 클래스 처음 발생 하는 경우 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="0ee18-132">사용자 지정 특성이 연결 된 경우는 `TypeDef` 또는 `MemberDef` 하는 (예: 멤버의 타임 스탬프) 컴파일 단위, 병합 되지 아니며 컴파일러에서 제거 하거나 해당 메타 데이터 업데이트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee18-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ee18-133">Requirements</span></span>  
 <span data-ttu-id="0ee18-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee18-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee18-135">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ee18-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ee18-136">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0ee18-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ee18-137">**.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee18-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee18-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ee18-138">See Also</span></span>  
 [<span data-ttu-id="0ee18-139">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ee18-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0ee18-140">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ee18-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
