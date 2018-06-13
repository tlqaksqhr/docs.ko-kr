---
title: IMetaDataAssemblyImport::EnumAssemblyRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a56d874e5e7ef491c24b0aef2ace700087de677
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447413"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="f8e5b-102">IMetaDataAssemblyImport::EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="f8e5b-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="f8e5b-103">열거는 `mdAssemblyRef` 어셈블리 매니페스트에서 정의 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8e5b-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8e5b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8e5b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f8e5b-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f8e5b-107">null 이어야 합니다 경우이 값은 `EnumAssemblyRefs` 메서드를 처음으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="f8e5b-108">[out] 열거 `mdAssemblyRef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f8e5b-109">[in] 에 추가할 수 있는 토큰의 최대 수는 `rAssemblyRefs` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f8e5b-110">[out] 토큰의 수에 실제로 배치 `rAssemblyRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8e5b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="f8e5b-111">Return Value</span></span>  
  
|<span data-ttu-id="f8e5b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8e5b-112">HRESULT</span></span>|<span data-ttu-id="f8e5b-113">설명</span><span class="sxs-lookup"><span data-stu-id="f8e5b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f8e5b-114">`EnumAssemblyRefs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f8e5b-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f8e5b-116">이 경우 `pcTokens` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8e5b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8e5b-117">Requirements</span></span>  
 <span data-ttu-id="f8e5b-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e5b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e5b-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8e5b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8e5b-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f8e5b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8e5b-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e5b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e5b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8e5b-122">See Also</span></span>  
 [<span data-ttu-id="f8e5b-123">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8e5b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
