---
title: "ICorThreadpool::CorCreateTimer 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorCreateTimer
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7a427396158fda7d387eecbeff58e6c1ef591dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="b250f-102">ICorThreadpool::CorCreateTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="b250f-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="b250f-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b250f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b250f-104">구문</span><span class="sxs-lookup"><span data-stu-id="b250f-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b250f-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b250f-105">Requirements</span></span>  
 <span data-ttu-id="b250f-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b250f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b250f-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b250f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b250f-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b250f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b250f-109">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b250f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b250f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b250f-110">See Also</span></span>  
 [<span data-ttu-id="b250f-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b250f-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
