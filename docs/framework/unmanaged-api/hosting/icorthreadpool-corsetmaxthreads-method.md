---
title: ICorThreadpool::CorSetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cbc14c1b84ae5605f7aaed688acbedbb51d056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437133"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="43e16-102">ICorThreadpool::CorSetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="43e16-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="43e16-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43e16-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e16-104">구문</span><span class="sxs-lookup"><span data-stu-id="43e16-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="43e16-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43e16-105">Requirements</span></span>  
 <span data-ttu-id="43e16-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43e16-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e16-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43e16-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43e16-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="43e16-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43e16-109">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e16-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e16-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43e16-110">See Also</span></span>  
 [<span data-ttu-id="43e16-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e16-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
