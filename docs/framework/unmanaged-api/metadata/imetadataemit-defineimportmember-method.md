---
title: "IMetaDataEmit::DefineImportMember 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bbe2c3144372ba66a0b3bad6198aefeeb7e12d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="0420a-102">IMetaDataEmit::DefineImportMember 메서드</span><span class="sxs-lookup"><span data-stu-id="0420a-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="0420a-103">형식이 나 현재 범위를 벗어난 정의 되 고 해당 참조에 대 한 토큰을 정의 하는 모듈의 지정된 된 멤버에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0420a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0420a-104">Syntax</span></span>  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0420a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0420a-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="0420a-106">[in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 대상 멤버를 가져올 어셈블리를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0420a-107">[in] 로 지정 된 어셈블리에 대 한 해시를 포함 하는 배열 `pAssemImport`합니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0420a-108">[in] `pbHashValue` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="0420a-109">[in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 대상 멤버를 가져올 메타 데이터 범위를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="0420a-110">[in] 대상 멤버를 지정 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="0420a-111">토큰 일 수 있습니다는 `mdMethodDef` (멤버 방법의 경우)에 대 한 `mdProperty` (에 대해 멤버 속성의 경우) 또는 `mdFieldDef` (멤버 필드)에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="0420a-112">[in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 대상 멤버를 가져올 어셈블리를 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="0420a-113">[in] `mdTypeRef` 또는 `mdModuleRef` 형식이 나 모듈에 대 한 토큰을 각각 소유 하는 대상 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="0420a-114">[out] `mdMemberRef` 멤버 참조에 대 한 현재 범위에 정의 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0420a-115">설명</span><span class="sxs-lookup"><span data-stu-id="0420a-115">Remarks</span></span>  
 <span data-ttu-id="0420a-116">`DefineImportMember` 메서드로 지정 된 멤버를 찾습니다 `mbMember`, 즉로 지정 된 다른 범위에 정의 된 `pImport`, 해당 속성을 검색 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="0420a-117">이 정보를 사용 하 여 호출 하 여 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 멤버 참조를 만들 수는 현재 범위에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="0420a-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="0420a-118">일반적으로 사용 하기 전에 `DefineImportMember` 메서드를 만들어야 합니다, 현재 범위, 형식 참조 또는 대상 멤버의 부모 클래스, 인터페이스 또는 모듈에 대 한 모듈 참조.</span><span class="sxs-lookup"><span data-stu-id="0420a-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="0420a-119">이 참조에 대 한 메타 데이터 토큰에 전달 됩니다는 `tkParent` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="0420a-120">컴파일러 또는 링커가 나중에 해결할 수는 대상 멤버의 부모에 대 한 참조를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="0420a-121">요약:</span><span class="sxs-lookup"><span data-stu-id="0420a-121">To summarize:</span></span>  
  
-   <span data-ttu-id="0420a-122">대상 멤버 필드 또는 메서드를 사용 중인 경우 하나는 [imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 또는 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) 방법을 사용에 대 한 현재 범위에 형식 참조를 만들 수는 멤버의 부모 클래스 또는 부모 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="0420a-123">사용 하 여 대상 멤버가 전역 변수 또는 전역 함수 (즉, 하지 멤버 클래스 또는 인터페이스의) 인 경우는 [imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) 멤버의 부모에 대 한 현재 범위에서 모듈 참조를 만드는 메서드를 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="0420a-124">대상 멤버의 부모에 의해 컴파일러 또는 링커 나중에 확인 될를 전달 합니다 `mdTokenNil` 에서 `tkParent`합니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="0420a-125">이 적용 되는 유일한 시나리오는 경우 전역 함수 또는 전역 변수를 현재 모듈에 연결 될.obj 파일에서 가져오는 및 메타 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0420a-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0420a-126">Requirements</span></span>  
 <span data-ttu-id="0420a-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0420a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0420a-128">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0420a-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0420a-129">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0420a-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0420a-130">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0420a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0420a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0420a-131">See Also</span></span>  
 [<span data-ttu-id="0420a-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0420a-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0420a-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0420a-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
