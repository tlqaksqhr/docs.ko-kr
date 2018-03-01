---
title: "ICorDebugStackWalk 인터페이스"
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
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 018ed69e52efd21ca25029284c70f1c8493d877f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="7b3e8-102">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b3e8-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="7b3e8-103">스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b3e8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-104">Methods</span></span>  
  
|<span data-ttu-id="7b3e8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-105">Method</span></span>|<span data-ttu-id="7b3e8-106">설명</span><span class="sxs-lookup"><span data-stu-id="7b3e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b3e8-107">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="7b3e8-108">현재 프레임에 대 한 컨텍스트를 반환 합니다.는 `ICorDebugStackWalk` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="7b3e8-109">SetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="7b3e8-110">설정의 `ICorDebugStackWalk` 개체의 현재 컨텍스트 스레드에 대 한 올바른 컨텍스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="7b3e8-111">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="7b3e8-112">이동 된 `ICorDebugStackWalk` 다음 프레임으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="7b3e8-113">GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="7b3e8-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="7b3e8-114">현재 프레임의 가져옵니다는 `ICorDebugStackWalk` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b3e8-115">설명</span><span class="sxs-lookup"><span data-stu-id="7b3e8-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b3e8-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b3e8-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b3e8-117">Requirements</span></span>  
 <span data-ttu-id="7b3e8-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b3e8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b3e8-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b3e8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b3e8-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b3e8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b3e8-121">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b3e8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3e8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b3e8-122">See Also</span></span>  
 [<span data-ttu-id="7b3e8-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b3e8-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7b3e8-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="7b3e8-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
