---
title: "IMetaDataEmit::SetTypeDefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a03b781865b55b832b34bfdab7c88ce33f4e9e12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="f082c-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f082c-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="f082c-103">이전 호출에서 정의 된 형식 기능을 설정 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f082c-104">구문</span><span class="sxs-lookup"><span data-stu-id="f082c-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f082c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f082c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f082c-106">[in] `mdTypeDef` 토큰에 대 한 원래 호출에서 얻은 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="f082c-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="f082c-108">이 비트 마스크의 `CorTypeAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="f082c-109">[in] `mdToken` 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="f082c-110">에 대 한 이전 호출에서 가져온 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), 또는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="f082c-111">[in] 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="f082c-112">이러한 `mdTypeRef` 토큰을 사용 하 여 가져오는 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="f082c-113">배열의 마지막 요소는 해야 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f082c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f082c-114">Requirements</span></span>  
 <span data-ttu-id="f082c-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f082c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f082c-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f082c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f082c-117">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f082c-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f082c-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f082c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f082c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f082c-119">See Also</span></span>  
 [<span data-ttu-id="f082c-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f082c-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f082c-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f082c-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
