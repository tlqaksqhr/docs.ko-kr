---
title: "IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59a4c13e84414dcd10b217134334777a745431c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="2e221-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="2e221-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="2e221-103">에 대 한이 콜백의 전송 하는 스레드는 호스트에 알려 줍니다 디버깅 서비스에서 차단 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e221-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e221-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e221-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e221-105">설명</span><span class="sxs-lookup"><span data-stu-id="2e221-105">Remarks</span></span>  
 <span data-ttu-id="2e221-106">`ThreadIsBlockingForDebugger` 메서드는 항상 런타임 스레드에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e221-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="2e221-107">`ThreadIsBlockingForDebugger` 메서드 사용 하면 호스트가 해당 스레드는 차단 하는 동안 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e221-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e221-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e221-108">Requirements</span></span>  
 <span data-ttu-id="2e221-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e221-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e221-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e221-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e221-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2e221-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e221-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e221-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e221-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e221-113">See Also</span></span>  
 [<span data-ttu-id="2e221-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e221-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
