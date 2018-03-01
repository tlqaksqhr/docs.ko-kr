---
title: "IMetaDataEmit::DefineNestedType 메서드"
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
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99250d98f9ffd90857128aa5d8a675a997926bf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="8f7fc-102">IMetaDataEmit::DefineNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="8f7fc-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="8f7fc-103">형식 정의의 메타 데이터 서명을 만듭니다, 반환 된 `mdTypeDef` 정의 된 형식에서 참조 형식의 멤버 임을 지정 하 고 해당 형식에 대 한 토큰는 `tdEncloser` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f7fc-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f7fc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f7fc-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="8f7fc-106">[in] 유니코드에 대 한 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="8f7fc-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="8f7fc-108">이 비트 마스크의 `CorTypeAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="8f7fc-109">[in] 기본 클래스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-109">[in] The token of the base class.</span></span> <span data-ttu-id="8f7fc-110">이 역할은 한 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="8f7fc-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="8f7fc-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="8f7fc-112">[in] 이 클래스 또는 인터페이스를 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="8f7fc-113">[in] 바깥쪽 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="8f7fc-114">배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="8f7fc-115">[out] `mdTypeDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7fc-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f7fc-116">Requirements</span></span>  
 <span data-ttu-id="8f7fc-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f7fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7fc-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f7fc-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f7fc-119">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8f7fc-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f7fc-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7fc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f7fc-121">See Also</span></span>  
 [<span data-ttu-id="8f7fc-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f7fc-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8f7fc-123">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f7fc-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
