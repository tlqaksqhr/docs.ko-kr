---
title: "IMetaDataTables::GetGuidHeapSize 메서드"
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
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 297b8f3572f67aa5e8b17b1b94d71f59962cfe68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="66b16-102">IMetaDataTables::GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="66b16-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="66b16-103">GUID 힙을 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66b16-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66b16-104">구문</span><span class="sxs-lookup"><span data-stu-id="66b16-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66b16-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66b16-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="66b16-106">[out] GUID 힙을 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66b16-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66b16-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66b16-107">Requirements</span></span>  
 <span data-ttu-id="66b16-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66b16-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66b16-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66b16-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66b16-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="66b16-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66b16-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66b16-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b16-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66b16-112">See Also</span></span>  
 [<span data-ttu-id="66b16-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66b16-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="66b16-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66b16-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
