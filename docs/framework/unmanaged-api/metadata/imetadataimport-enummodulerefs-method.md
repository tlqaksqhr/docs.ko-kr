---
title: "IMetaDataImport::EnumModuleRefs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumModuleRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 782b363ddf518d45ac5e5fc2b2e4b1c68aff8ea3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="eb677-102">IMetaDataImport::EnumModuleRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="eb677-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="eb677-103">가져온 모듈을 나타내는 ModuleRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb677-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb677-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb677-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb677-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eb677-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="eb677-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="eb677-108">[out] ModuleRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eb677-109">[in] `rModuleRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="eb677-110">[out] 반환 된 ModuleRef 토큰 수 `rModuleRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb677-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="eb677-111">Return Value</span></span>  
  
|<span data-ttu-id="eb677-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb677-112">HRESULT</span></span>|<span data-ttu-id="eb677-113">설명</span><span class="sxs-lookup"><span data-stu-id="eb677-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eb677-114">`EnumModuleRefs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eb677-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="eb677-116">이 경우 `pcModuleRefs` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb677-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb677-117">Requirements</span></span>  
 <span data-ttu-id="eb677-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb677-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb677-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb677-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb677-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eb677-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb677-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb677-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb677-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb677-122">See Also</span></span>  
 [<span data-ttu-id="eb677-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb677-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="eb677-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb677-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
