---
title: IMetaDataImport::EnumModuleRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 294156983507476b7ddfda3bc3cad16bb32f422b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445411"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="94500-102">IMetaDataImport::EnumModuleRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="94500-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="94500-103">가져온 모듈을 나타내는 ModuleRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="94500-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94500-104">구문</span><span class="sxs-lookup"><span data-stu-id="94500-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94500-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94500-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="94500-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94500-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="94500-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94500-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="94500-108">[out] ModuleRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="94500-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="94500-109">[in] `rModuleRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="94500-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="94500-110">[out] 반환 된 ModuleRef 토큰 수 `rModuleRefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="94500-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94500-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="94500-111">Return Value</span></span>  
  
|<span data-ttu-id="94500-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94500-112">HRESULT</span></span>|<span data-ttu-id="94500-113">설명</span><span class="sxs-lookup"><span data-stu-id="94500-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="94500-114">`EnumModuleRefs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="94500-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="94500-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94500-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="94500-116">이 경우 `pcModuleRefs` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="94500-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94500-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94500-117">Requirements</span></span>  
 <span data-ttu-id="94500-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94500-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94500-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94500-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94500-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="94500-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94500-121">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94500-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94500-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94500-122">See Also</span></span>  
 [<span data-ttu-id="94500-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94500-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="94500-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94500-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
