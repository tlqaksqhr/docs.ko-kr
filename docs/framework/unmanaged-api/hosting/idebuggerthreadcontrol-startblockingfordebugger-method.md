---
title: "IDebuggerThreadControl::StartBlockingForDebugger 메서드"
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
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99c0bc78705fa07883d92bf0cc1d90300c5ac549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="f9a0f-102">IDebuggerThreadControl::StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="f9a0f-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="f9a0f-103">디버깅 서비스 시작 모든 스레드를 차단 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0f-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9a0f-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9a0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9a0f-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="f9a0f-106">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0f-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9a0f-107">설명</span><span class="sxs-lookup"><span data-stu-id="f9a0f-107">Remarks</span></span>  
 <span data-ttu-id="f9a0f-108">`StartBlockingForDebugger` 메서드는 런타임 스레드에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0f-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a0f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9a0f-109">Requirements</span></span>  
 <span data-ttu-id="f9a0f-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a0f-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9a0f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9a0f-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f9a0f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9a0f-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a0f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9a0f-114">See Also</span></span>  
 [<span data-ttu-id="f9a0f-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9a0f-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
