---
title: "IMetaDataAssemblyImport::GetManifestResourceProps 메서드"
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
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ba9af4abca111b94a678c48d236a53dc6313b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="ae41b-102">IMetaDataAssemblyImport::GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ae41b-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="ae41b-103">지정 된 메타 데이터 서명 가진 매니페스트 리소스의 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae41b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae41b-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae41b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae41b-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="ae41b-106">[in] `mdManifestResource` 토큰을 가져올 속성에 대 한 리소스를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ae41b-107">[out] 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ae41b-108">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ae41b-109">[out] 와이드 문자에 실제로 반환 된 수에 대 한 포인터 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ae41b-110">[out] 에 대 한 포인터는 `mdFile` 토큰 또는 `mdAssemblyRef` 리소스가 포함 된 파일 또는 어셈블리를 각각 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="ae41b-111">[out] 파일 내에서 리소스의 시작 부분에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="ae41b-112">[out] 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="ae41b-113">플래그 값은 하나 이상의 조합 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae41b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae41b-114">Requirements</span></span>  
 <span data-ttu-id="ae41b-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae41b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae41b-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ae41b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae41b-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ae41b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae41b-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae41b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae41b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae41b-119">See Also</span></span>  
 [<span data-ttu-id="ae41b-120">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae41b-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
