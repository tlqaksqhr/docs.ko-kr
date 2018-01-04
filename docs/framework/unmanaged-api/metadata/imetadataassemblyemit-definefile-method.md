---
title: "IMetaDataAssemblyEmit::DefineFile 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineFile
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48584822d7a2f31c466401db3a24156a71ad7011
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="04b24-102">IMetaDataAssemblyEmit::DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="04b24-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="04b24-103">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04b24-104">구문</span><span class="sxs-lookup"><span data-stu-id="04b24-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04b24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04b24-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="04b24-106">[in] 사용할 수 있도록 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="04b24-107">[in] 어셈블리와 연결 된 데이터 해시에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="04b24-108">[in] 바이트 크기 `pbHashValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="04b24-109">[in] 비트 조합 `FileFlags` 속성 설정을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="04b24-110">[out] 반환 된에 대 한 포인터 `File` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04b24-111">설명</span><span class="sxs-lookup"><span data-stu-id="04b24-111">Remarks</span></span>  
 <span data-ttu-id="04b24-112">하나의 `File` 이 어셈블리는 메타 데이터를 포함 하는 파일 제외 하 고 작성 된 시간에이 어셈블리의 일부인 각 파일에 대 한 메타 데이터 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04b24-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04b24-113">Requirements</span></span>  
 <span data-ttu-id="04b24-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04b24-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b24-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04b24-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04b24-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="04b24-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04b24-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04b24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b24-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04b24-118">See Also</span></span>  
 [<span data-ttu-id="04b24-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04b24-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
