---
title: "IMetaDataTables::GetNextBlob 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399cf6626e7a56584829b2a8417958ce7e608727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="23418-102">IMetaDataTables::GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="23418-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="23418-103">테이블에 다음 이진 대형 개체 (BLOB)의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23418-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23418-104">구문</span><span class="sxs-lookup"><span data-stu-id="23418-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23418-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23418-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="23418-106">[in] Blob의 열에서 반환 된 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="23418-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="23418-107">[out] 추가 BLOB의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="23418-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23418-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23418-108">Requirements</span></span>  
 <span data-ttu-id="23418-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23418-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23418-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23418-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23418-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="23418-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23418-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23418-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23418-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23418-113">See Also</span></span>  
 [<span data-ttu-id="23418-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23418-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="23418-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23418-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
