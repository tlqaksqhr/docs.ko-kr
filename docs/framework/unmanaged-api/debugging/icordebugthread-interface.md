---
title: ICorDebugThread Interface1
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
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="bb956-102">ICorDebugThread Interface1</span><span class="sxs-lookup"><span data-stu-id="bb956-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="bb956-103">프로세스의 스레드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-103">Represents a thread in a process.</span></span> <span data-ttu-id="bb956-104">`ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb956-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-105">Methods</span></span>  
  
|<span data-ttu-id="bb956-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-106">Method</span></span>|<span data-ttu-id="bb956-107">설명</span><span class="sxs-lookup"><span data-stu-id="bb956-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb956-108">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="bb956-109">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-109">This method is not implemented.</span></span> <span data-ttu-id="bb956-110">이 메서드를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bb956-110">Do not use it.</span></span>|  
|[<span data-ttu-id="bb956-111">CreateEval 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="bb956-112">이 작동 하는 ICorDebugEval 개체를 만듭니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-113">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="bb956-114">이 활성 프레임을 단계별로 실행을 허용 하는 ICorDebugStepper 개체를 만듭니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-115">EnumerateChains 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="bb956-116">이 스택 체인을 모두 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-117">GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="bb956-118">이 활성 ICorDebugChain에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-119">GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="bb956-120">이 활성 ICorDebugFrame에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-121">GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="bb956-122">이 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 현재 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="bb956-123">GetCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="bb956-124">현재 관리 되는 코드에 의해 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="bb956-125">GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="bb956-126">이 현재 디버그 상태를 설명 하는 CorDebugThreadState 값을 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-127">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="bb956-128">이의 활성 부분에 대 한 현재 핸들을 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-129">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="bb956-130">이의 활성 부분의 현재 운영 체제 식별자를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-131">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="bb956-132">공용 언어 런타임 (CLR) 스레드에서에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="bb956-133">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="bb956-134">이 프로세스에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 일부를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="bb956-135">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="bb956-136">이 연결 된 레지스터 세트에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-137">GetUserState 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="bb956-138">이 항목의 현재 상태를 설명 하는 CorDebugUserState 값의 비트 조합 가져옵니다 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="bb956-139">SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="bb956-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="bb956-140">설정의 비트 조합 `CorDebugThreadState` 이 디버깅 상태를 설명 하는 값 `ICorDebugThread`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb956-141">설명</span><span class="sxs-lookup"><span data-stu-id="bb956-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb956-142">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb956-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb956-143">Requirements</span></span>  
 <span data-ttu-id="bb956-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb956-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb956-145">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb956-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb956-146">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb956-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb956-147">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb956-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb956-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb956-148">See Also</span></span>  
 [<span data-ttu-id="bb956-149">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb956-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
