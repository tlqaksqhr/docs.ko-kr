---
title: "IMetaDataAssemblyEmit::DefineExportedType 메서드"
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
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59aae188e404ebc717a140fb7918e3fbf69f3f70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="f3fd5-102">IMetaDataAssemblyEmit::DefineExportedType 메서드</span><span class="sxs-lookup"><span data-stu-id="f3fd5-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="f3fd5-103">지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3fd5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3fd5-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3fd5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3fd5-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f3fd5-106">[in] 내보낼 수 있는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="f3fd5-107">공용 언어 런타임 내보낸 형식의 이름은의 버전 1.1에 지정 된 이름과 정확히 일치 해야에 대 한는 `TypeDef` 유형에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="f3fd5-108">[in] 내보낸된 형식을 구현 하는 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="f3fd5-109">유효한 값 및 관련된 의미는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="f3fd5-110">`mdFile`형식이이 어셈블리 내의 다른 파일에 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="f3fd5-111">`mdAssemblyRef`형식이 다른 어셈블리에 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="f3fd5-112">`mdExportedTYpe`형식이 다른 형식에 중첩 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="f3fd5-113">`mdFileNil`매니페스트와 같은 파일에 형식과 중첩 된 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="f3fd5-114">[in] 내보낼 형식을 지정 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="f3fd5-115">이 값은 입력의 `TypeDef` 형식을 구현 하 고이 파일은이 어셈블리의 경우에 해당 하는 파일에는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="f3fd5-116">[in] 비트 조합 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 내보낸된 형식에 대 한 속성 설정을 정의 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="f3fd5-117">[out] 내보낸된 형식을 나타내는 반환 된 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3fd5-118">설명</span><span class="sxs-lookup"><span data-stu-id="f3fd5-118">Remarks</span></span>  
 <span data-ttu-id="f3fd5-119">`ExportedType` 이 어셈블리에 의해 노출 되는 매니페스트를 포함 하는 것과 다른 모듈에 구현 되는 각 형식에 대 한 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3fd5-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3fd5-120">Requirements</span></span>  
 <span data-ttu-id="f3fd5-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3fd5-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3fd5-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3fd5-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3fd5-123">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f3fd5-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3fd5-124">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3fd5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3fd5-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3fd5-125">See Also</span></span>  
 [<span data-ttu-id="f3fd5-126">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3fd5-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
