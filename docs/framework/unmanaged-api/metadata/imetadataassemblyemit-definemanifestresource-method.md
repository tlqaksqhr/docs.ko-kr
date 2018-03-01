---
title: "IMetaDataAssemblyEmit::DefineManifestResource 메서드"
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
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a435c946e13950faad7545e3da78ce373ee7fa0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="58c07-102">IMetaDataAssemblyEmit::DefineManifestResource 메서드</span><span class="sxs-lookup"><span data-stu-id="58c07-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="58c07-103">지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c07-104">구문</span><span class="sxs-lookup"><span data-stu-id="58c07-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58c07-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58c07-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="58c07-106">[in] 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="58c07-107">[in] 형식의 메타 데이터 토큰이 `mdtFile` 또는 `mdtAssemblyRef` 리소스 공급자에 매핑되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="58c07-108">NULL 값을 메타 데이터가 포함 된 파일의 리소스 공급자 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="58c07-109">[in] 파일 내에서 리소스의 시작 부분에 대 한 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="58c07-110">독립 실행형 파일에서 리소스에 대 한이 항상 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="58c07-111">리소스는 PE (이식 가능한 실행) 파일에 포함 된 경우 BLOB cor.h 헤더 파일에 지정 된 위치에서 시작 하는 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="58c07-112">[in] 리소스 정의 대 한 속성 설정을 지정 하는 플래그 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="58c07-113">[out] 반환 된 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58c07-114">설명</span><span class="sxs-lookup"><span data-stu-id="58c07-114">Remarks</span></span>  
 <span data-ttu-id="58c07-115">하나의 `ManifestResource` 각 어셈블리의 파일에서 구현 되는 각 리소스에 대 한 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c07-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58c07-116">Requirements</span></span>  
 <span data-ttu-id="58c07-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58c07-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c07-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58c07-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58c07-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="58c07-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58c07-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c07-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c07-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58c07-121">See Also</span></span>  
 [<span data-ttu-id="58c07-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58c07-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
