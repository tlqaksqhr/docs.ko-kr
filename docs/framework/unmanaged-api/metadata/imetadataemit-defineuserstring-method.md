---
title: "IMetaDataEmit::DefineUserString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 729f2d48722fb34b844636b416edf36d715e1a48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="89f64-102">IMetaDataEmit::DefineUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="89f64-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="89f64-103">지정된 된 리터럴 문자열에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89f64-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f64-104">구문</span><span class="sxs-lookup"><span data-stu-id="89f64-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89f64-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89f64-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="89f64-106">[in] 저장할 사용자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="89f64-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="89f64-107">[in] 와이드 문자 개수 `szString`합니다.</span><span class="sxs-lookup"><span data-stu-id="89f64-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="89f64-108">[out] 할당 된 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="89f64-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f64-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89f64-109">Requirements</span></span>  
 <span data-ttu-id="89f64-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89f64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f64-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89f64-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89f64-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="89f64-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89f64-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f64-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89f64-114">See Also</span></span>  
 [<span data-ttu-id="89f64-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89f64-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="89f64-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89f64-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
