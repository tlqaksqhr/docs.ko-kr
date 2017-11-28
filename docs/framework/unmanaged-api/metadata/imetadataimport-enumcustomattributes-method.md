---
title: "IMetaDataImport::EnumCustomAttributes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 78a642ab3c9766ba32537e24814b3b0536df67c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="284c8-102">IMetaDataImport::EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="284c8-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="284c8-103">지정 된 형식 또는 멤버와 연결 된 사용자 지정 특성 정의 토큰을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="284c8-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="284c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="284c8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="284c8-106">[out에서] 반환 된 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="284c8-107">[in] 열거형 또는 모든 사용자 지정 특성에 대 한 0의 범위에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="284c8-108">[in] 특성을 열거할 수의 형식의 생성자에 대 한 토큰 또는 `null` 모든 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="284c8-109">[out] 사용자 지정 특성 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="284c8-110">[in] `rCustomAttributes` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="284c8-111">[out, optional] 반환 된 토큰 값의 실제 수 `rCustomAttributes`합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="284c8-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="284c8-112">Return Value</span></span>  
  
|<span data-ttu-id="284c8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="284c8-113">HRESULT</span></span>|<span data-ttu-id="284c8-114">설명</span><span class="sxs-lookup"><span data-stu-id="284c8-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="284c8-115">`EnumCustomAttributes`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="284c8-116">열거를 사용자 지정 특성이 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="284c8-117">이 경우 `pcCustomAttributes` 은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="284c8-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="284c8-118">Requirements</span></span>  
 <span data-ttu-id="284c8-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="284c8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="284c8-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="284c8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="284c8-121">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="284c8-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="284c8-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="284c8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="284c8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="284c8-123">See Also</span></span>  
 [<span data-ttu-id="284c8-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="284c8-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="284c8-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="284c8-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
