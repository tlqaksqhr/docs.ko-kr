---
title: "IDebuggerThreadControl::StartBlockingForDebugger 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.StartBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0f7d49766c68c24441bf59d2d83958276def0143
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="e9f95-102">IDebuggerThreadControl::StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="e9f95-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="e9f95-103">디버깅 서비스 시작 모든 스레드를 차단 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e9f95-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f95-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9f95-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9f95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9f95-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="e9f95-106">[in] 나중에 사용할 수는 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f95-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9f95-107">설명</span><span class="sxs-lookup"><span data-stu-id="e9f95-107">Remarks</span></span>  
 <span data-ttu-id="e9f95-108">`StartBlockingForDebugger` 메서드는 런타임 스레드에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f95-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f95-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9f95-109">Requirements</span></span>  
 <span data-ttu-id="e9f95-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f95-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f95-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9f95-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9f95-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e9f95-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9f95-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f95-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9f95-114">See Also</span></span>  
 [<span data-ttu-id="e9f95-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9f95-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
