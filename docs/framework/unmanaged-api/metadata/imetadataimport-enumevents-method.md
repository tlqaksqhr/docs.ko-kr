---
title: "IMetaDataImport::EnumEvents 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumEvents
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed783cf80fb068656855c2c06ab814f665f1cede
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="9b956-102">IMetaDataImport::EnumEvents 메서드</span><span class="sxs-lookup"><span data-stu-id="9b956-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="9b956-103">지정한 TypeDef 토큰에 대한 이벤트 정의 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b956-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b956-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b956-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b956-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9b956-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="9b956-107">[in] 열거할 수 있는 이벤트 정의 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="9b956-108">[out] 반환 된 이벤트의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9b956-109">[in] `rEvents` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="9b956-110">[out] 반환 되는 이벤트의 실제 수 `rEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b956-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b956-111">Return Value</span></span>  
  
|<span data-ttu-id="9b956-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b956-112">HRESULT</span></span>|<span data-ttu-id="9b956-113">설명</span><span class="sxs-lookup"><span data-stu-id="9b956-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9b956-114">`EnumEvents`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9b956-115">이벤트가 열거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-115">There are no events to enumerate.</span></span> <span data-ttu-id="9b956-116">이 경우 `pcEvents` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b956-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b956-117">Requirements</span></span>  
 <span data-ttu-id="9b956-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b956-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b956-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b956-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b956-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9b956-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b956-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b956-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b956-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b956-122">See Also</span></span>  
 [<span data-ttu-id="9b956-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b956-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9b956-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b956-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
