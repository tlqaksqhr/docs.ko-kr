---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b3623c886a48cc938be017f955fbdac1df3f10f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437637"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="a5711-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="a5711-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="a5711-103">디버깅 서비스 차단 되는 모든 스레드를 해제 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a5711-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5711-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5711-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a5711-105">설명</span><span class="sxs-lookup"><span data-stu-id="a5711-105">Remarks</span></span>  
 <span data-ttu-id="a5711-106">`ReleaseAllRuntimeThreads` 메서드는 런타임 스레드에서 호출 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5711-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="a5711-107">호스트에는 런타임 스레드 차단, 스레드를 해제 해야 이제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5711-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5711-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5711-108">Requirements</span></span>  
 <span data-ttu-id="a5711-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5711-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5711-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a5711-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5711-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a5711-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5711-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5711-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5711-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5711-113">See Also</span></span>  
 [<span data-ttu-id="a5711-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5711-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
