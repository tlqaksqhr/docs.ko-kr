---
title: "IMetaDataAssemblyEmit::SetAssemblyProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aab505700b669cae071420117abd71332f49d8b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="e2ddc-102">IMetaDataAssemblyEmit::SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e2ddc-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="e2ddc-103">지정된 `Assembly` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ddc-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2ddc-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2ddc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2ddc-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="e2ddc-106">[in] 메타 데이터 토큰을 지정 하는 `Assembly` 메타 데이터 구조를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="e2ddc-107">[in] 어셈블리의 게시자의 공개 키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="e2ddc-108">[in] 바이트 크기 `pbPublicKey`합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="e2ddc-109">[in] 어셈블리 파일을 해시 하는 데 사용 되는 해시 알고리즘에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="e2ddc-110">[in] 어셈블리의 이해 하기 쉬운 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="e2ddc-111">[in] 포인터 ASSEMBLYMETADATA 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="e2ddc-112">[in] 비트 조합 [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) 어셈블리의 다양 한 특성을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2ddc-113">설명</span><span class="sxs-lookup"><span data-stu-id="e2ddc-113">Remarks</span></span>  
 <span data-ttu-id="e2ddc-114">만들려는 `Assembly` 메타 데이터 구조를 사용 하 여는 [imetadataassemblyemit:: Defineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ddc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2ddc-115">Requirements</span></span>  
 <span data-ttu-id="e2ddc-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ddc-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ddc-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2ddc-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2ddc-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e2ddc-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2ddc-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ddc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ddc-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2ddc-120">See Also</span></span>  
 [<span data-ttu-id="e2ddc-121">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2ddc-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
