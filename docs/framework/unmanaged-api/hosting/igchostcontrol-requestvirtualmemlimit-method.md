---
title: "IGCHostControl::RequestVirtualMemLimit 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHostControl.RequestVirtualMemLimit
api_location: mscoree.dll
api_type: COM
f1_keywords: RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4892cf5dc3a3663f1bccc95d1975bfe96277faa5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="5242b-102">IGCHostControl::RequestVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="5242b-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="5242b-103">호스트에 가상 메모리의 한계를 변경 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5242b-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5242b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5242b-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5242b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5242b-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="5242b-106">[in] 메모리 할당의 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5242b-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="5242b-107">[out에서] 할당 된 메모리의 실제 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5242b-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5242b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5242b-108">Requirements</span></span>  
 <span data-ttu-id="5242b-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5242b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5242b-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5242b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5242b-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5242b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5242b-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5242b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5242b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5242b-113">See Also</span></span>  
 [<span data-ttu-id="5242b-114">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5242b-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
