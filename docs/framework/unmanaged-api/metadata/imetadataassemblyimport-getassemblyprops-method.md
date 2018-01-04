---
title: "IMetaDataAssemblyImport::GetAssemblyProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e99474fea329f53286d698d0e1a302909d5cc65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="71648-102">IMetaDataAssemblyImport::GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="71648-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="71648-103">지정한 메타 데이터 서명 사용 하 여 어셈블리에 대 한 속성의 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71648-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71648-104">구문</span><span class="sxs-lookup"><span data-stu-id="71648-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71648-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71648-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="71648-106">[in].</span><span class="sxs-lookup"><span data-stu-id="71648-106">[in].</span></span> <span data-ttu-id="71648-107">`mdAssembly` 메타 데이터 토큰을 가져올 속성에 대 한 어셈블리를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="71648-108">[out] 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="71648-109">[out] 반환 된 공개 키의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="71648-110">[out] 어셈블리의 파일을 해시 하는 데 사용 된 알고리즘에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="71648-111">[out] 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="71648-112">[in] 와이드 문자에서 크기의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="71648-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="71648-113">[out] 와이드 문자에 실제로 반환 된 수가 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="71648-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="71648-114">[out] 어셈블리 메타 데이터가 포함 된 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="71648-115">[out] 어셈블리에 적용할 메타 데이터를 설명 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="71648-116">이 값은 하나 이상의 조합 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71648-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71648-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71648-117">Requirements</span></span>  
 <span data-ttu-id="71648-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71648-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71648-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71648-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71648-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="71648-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71648-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71648-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71648-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71648-122">See Also</span></span>  
 [<span data-ttu-id="71648-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71648-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
