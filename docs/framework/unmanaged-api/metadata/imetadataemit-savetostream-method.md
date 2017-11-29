---
title: "IMetaDataEmit::SaveToStream 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SaveToStream
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 97f65fb6cfb7067ed4e6929772f0f114cedcf787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="29b9a-102">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="29b9a-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="29b9a-103">지정 된 현재 범위에서 모든 메타 데이터를 저장 `IStream`합니다.</span><span class="sxs-lookup"><span data-stu-id="29b9a-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="29b9a-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29b9a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29b9a-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="29b9a-106">[in] 에 저장 하는 쓰기 가능한 스트림.</span><span class="sxs-lookup"><span data-stu-id="29b9a-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="29b9a-107">[in] 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b9a-107">[in] Reserved.</span></span> <span data-ttu-id="29b9a-108">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b9a-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29b9a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29b9a-109">Requirements</span></span>  
 <span data-ttu-id="29b9a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29b9a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29b9a-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="29b9a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29b9a-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="29b9a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29b9a-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29b9a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b9a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29b9a-114">See Also</span></span>  
 [<span data-ttu-id="29b9a-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29b9a-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="29b9a-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29b9a-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
