---
title: "IGCHost::GetThreadStats 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetThreadStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7bfd6b89c3220e071a477e0c5b85e4ee57289762
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="fc6f3-102">IGCHost::GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="fc6f3-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="fc6f3-103">가비지 수집에 대 한 스레드 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc6f3-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc6f3-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc6f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc6f3-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="fc6f3-106">[in] 통계를 검색 하려는 스레드를 지정 하는 파이버 쿠키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc6f3-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="fc6f3-107">[out에서] 에 대 한 포인터는 [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) 지정 된 스레드에 대 한 가비지 수집 통계를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="fc6f3-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6f3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc6f3-108">Requirements</span></span>  
 <span data-ttu-id="fc6f3-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc6f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc6f3-110">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="fc6f3-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fc6f3-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fc6f3-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc6f3-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6f3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc6f3-113">See Also</span></span>  
 [<span data-ttu-id="fc6f3-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc6f3-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
