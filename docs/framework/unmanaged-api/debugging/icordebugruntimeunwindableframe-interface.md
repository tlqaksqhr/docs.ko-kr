---
title: "ICorDebugRuntimeUnwindableFrame 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80b4212691784d88c92235a5c5c65acaee165201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="95f2c-102">ICorDebugRuntimeUnwindableFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95f2c-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="95f2c-103">프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f2c-104">설명</span><span class="sxs-lookup"><span data-stu-id="95f2c-104">Remarks</span></span>  
 <span data-ttu-id="95f2c-105">`ICorDebugRuntimeUnwindableFrame`ICorDebugFrame 인터페이스의 특수 버전이입니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="95f2c-106">현재 스택의 프레임을 해제 하려면 런타임 필요로 하는 관리 되지 않는 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="95f2c-107">기존 해제 규칙 JIT 컴파일된 코드를 사용 하지 않으므로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="95f2c-108">사용 하도록 해제할 수 있는 프레임을 인식 하는 디버거는 [icordebugstackwalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) , 하지만 해제 메서드 자체는 검사를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="95f2c-109">디버거 받을 때는 `ICorDebugRuntimeUnwindableFrame`, 호출할 수는 [icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 프레임의 컨텍스트를 검색 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f2c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95f2c-110">Requirements</span></span>  
 <span data-ttu-id="95f2c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95f2c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f2c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95f2c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95f2c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f2c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f2c-114">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f2c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f2c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95f2c-115">See Also</span></span>  
 [<span data-ttu-id="95f2c-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95f2c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="95f2c-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="95f2c-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
