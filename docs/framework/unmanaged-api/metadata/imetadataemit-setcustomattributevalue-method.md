---
title: "IMetaDataEmit::SetCustomAttributeValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetCustomAttributeValue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 30538b0f6f6aa196edf8373f5f4e6f09ba903223
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="8b254-102">IMetaDataEmit::SetCustomAttributeValue 메서드</span><span class="sxs-lookup"><span data-stu-id="8b254-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="8b254-103">설정에 대 한 이전 호출에서 정의한 사용자 지정 특성의 값을 업데이트 하거나 [imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b254-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b254-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b254-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b254-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b254-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="8b254-106">[in] 대상 사용자 지정 특성의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8b254-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="8b254-107">[in] 사용자 지정 특성을 포함 하는 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b254-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="8b254-108">[in] 사용자 지정 특성의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8b254-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b254-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b254-109">Requirements</span></span>  
 <span data-ttu-id="8b254-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b254-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b254-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b254-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b254-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8b254-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b254-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b254-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b254-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b254-114">See Also</span></span>  
 [<span data-ttu-id="8b254-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b254-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8b254-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b254-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
