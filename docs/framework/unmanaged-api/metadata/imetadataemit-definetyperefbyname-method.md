---
title: IMetaDataEmit::DefineTypeRefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4fd6102b65137a06009428c1245b80c0d44924a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445493"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="b5b89-102">IMetaDataEmit::DefineTypeRefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="b5b89-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="b5b89-103">현재 범위 밖에 있는 지정된 된 범위에 정의 된 형식에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b89-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5b89-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5b89-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5b89-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="b5b89-106">[in] 결정 범위를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="b5b89-107">다음 토큰 형식을 유효한은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="b5b89-108">`mdModuleRef`는 형식이 호출자에 게 정의 되어 있는 동일한 어셈블리에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="b5b89-109">`mdAssemblyRef`는 형식이 호출자에 게 정의 되어 있는 것과 다른 어셈블리에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="b5b89-110">`mdTypeRef`는 형식이 중첩된 형식이 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="b5b89-111">`mdModule`형식을 호출자가 정의 하는 동일한 모듈에 정의 된 경우.</span><span class="sxs-lookup"><span data-stu-id="b5b89-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="b5b89-112">전역으로 정의 된 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5b89-113">[in] 유니코드에서는 대상 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="b5b89-114">[out] 에 대 한 포인터는 `mdTypeRef` 토큰 형식에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b89-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5b89-115">Requirements</span></span>  
 <span data-ttu-id="b5b89-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5b89-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b89-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5b89-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5b89-118">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b5b89-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5b89-119">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5b89-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b89-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5b89-120">See Also</span></span>  
 [<span data-ttu-id="b5b89-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5b89-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b5b89-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5b89-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
