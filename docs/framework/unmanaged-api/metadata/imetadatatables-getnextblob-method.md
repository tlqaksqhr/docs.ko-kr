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
ms.openlocfilehash: 151fdf06f6203eabf2fc3e37bd30399b52394124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="9917d-102">IMetaDataTables::GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="9917d-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="9917d-103">테이블에 다음 이진 대형 개체 (BLOB)의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9917d-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9917d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9917d-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9917d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9917d-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="9917d-106">[in] Blob의 열에서 반환 된 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="9917d-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9917d-107">[out] 추가 BLOB의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9917d-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9917d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9917d-108">Requirements</span></span>  
 <span data-ttu-id="9917d-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9917d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9917d-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9917d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9917d-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9917d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9917d-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9917d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9917d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9917d-113">See Also</span></span>  
 [<span data-ttu-id="9917d-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9917d-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="9917d-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9917d-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
