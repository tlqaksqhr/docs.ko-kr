---
title: "IMetaDataTables::GetBlobHeapSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 176d924ec117365408a31f1bfc38901a7ef2cf65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="74eec-102">IMetaDataTables::GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="74eec-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="74eec-103">(BLOB) 이진 대형 개체 힙 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74eec-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74eec-104">구문</span><span class="sxs-lookup"><span data-stu-id="74eec-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="74eec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74eec-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="74eec-106">[out] BLOB 힙을 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74eec-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74eec-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74eec-107">Requirements</span></span>  
 <span data-ttu-id="74eec-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74eec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74eec-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74eec-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74eec-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="74eec-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74eec-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74eec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eec-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74eec-112">See Also</span></span>  
 [<span data-ttu-id="74eec-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74eec-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="74eec-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74eec-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
