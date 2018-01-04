---
title: "IMetaDataAssemblyEmit::DefineAssembly 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35bc85cdc4380ee112b7095866c05e5d7639200b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="f922f-102">IMetaDataAssemblyEmit::DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="f922f-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="f922f-103">만듭니다는 `Assembly` 지정된 된 어셈블리에 대 한 포함 된 메타 데이터 구조 및 관련된 메타 데이터 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f922f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f922f-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f922f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f922f-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="f922f-106">[in] 어셈블리가 강력 하 게 지정 하지 않은 경우 어셈블리 또는 NULL의 게시자를 식별 하는 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="f922f-107">[in] 바이트 크기 `pbPublicKey`합니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="f922f-108">[in] Sha-1 알고리즘을 지정 하려면 어셈블리 또는 NULL의 파일을 암호화 하는 데 해시 알고리즘의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="f922f-109">[in] 어셈블리의 이해 하기 쉬운 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="f922f-110">이 값은 1024 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f922f-111">[in] 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="f922f-112">[in] 조합을 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 은 어셈블리의 기능을 설명 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="f922f-113">[out] 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f922f-114">설명</span><span class="sxs-lookup"><span data-stu-id="f922f-114">Remarks</span></span>  
 <span data-ttu-id="f922f-115">하나의 `Assembly` 매니페스트 메타 데이터 구조를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f922f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f922f-116">Requirements</span></span>  
 <span data-ttu-id="f922f-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f922f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f922f-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f922f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f922f-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f922f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f922f-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f922f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f922f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f922f-121">See Also</span></span>  
 [<span data-ttu-id="f922f-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f922f-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
