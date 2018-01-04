---
title: "IMetaDataAssemblyImport::FindManifestResourceByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindManifestResourceByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d6cc738c227157b45e242fb46a672d28d6ce778
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="8b2f4-102">IMetaDataAssemblyImport::FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="8b2f4-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="8b2f4-103">지정 된 이름의 매니페스트 리소스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b2f4-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b2f4-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b2f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b2f4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8b2f4-106">[in] 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2f4-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="8b2f4-107">[out] 배열을 저장 하는 데는 `mdManifestResource` 매니페스트 리소스를 나타내는 각각의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8b2f4-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b2f4-108">설명</span><span class="sxs-lookup"><span data-stu-id="8b2f4-108">Remarks</span></span>  
 <span data-ttu-id="8b2f4-109">`FindManifestResourceByName` 메서드는 참조를 확인 하기 위한 공용 언어 런타임에서 표준 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2f4-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2f4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b2f4-110">Requirements</span></span>  
 <span data-ttu-id="8b2f4-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b2f4-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2f4-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b2f4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b2f4-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8b2f4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b2f4-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2f4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b2f4-115">See Also</span></span>  
 [<span data-ttu-id="8b2f4-116">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b2f4-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="8b2f4-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="8b2f4-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
