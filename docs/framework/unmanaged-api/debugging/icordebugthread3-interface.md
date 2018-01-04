---
title: "ICorDebugThread3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3
helpviewer_keywords: ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cfb3267637210567f3df9fa08bb75135dc585ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="f3578-102">ICorDebugThread3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3578-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="f3578-103">진입점을 제공 된 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 및 해당 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3578-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f3578-104">Methods</span></span>  
  
|<span data-ttu-id="f3578-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f3578-105">Method</span></span>|<span data-ttu-id="f3578-106">설명</span><span class="sxs-lookup"><span data-stu-id="f3578-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3578-107">CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="f3578-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="f3578-108">만듭니다는 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 해당 스택 해제 하려는 스레드에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="f3578-109">GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="f3578-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="f3578-110">내부 프레임의 배열을 반환 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체)를 스택에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3578-111">설명</span><span class="sxs-lookup"><span data-stu-id="f3578-111">Remarks</span></span>  
 <span data-ttu-id="f3578-112">`ICorDebugThread3`ICorDebugThread 인터페이스를 논리적으로 확장이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3578-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3578-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3578-114">Requirements</span></span>  
 <span data-ttu-id="f3578-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3578-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3578-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3578-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3578-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3578-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3578-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3578-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3578-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3578-119">See Also</span></span>  
 [<span data-ttu-id="f3578-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3578-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f3578-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="f3578-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
