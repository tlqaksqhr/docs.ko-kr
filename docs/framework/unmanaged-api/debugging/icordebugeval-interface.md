---
title: ICorDebugEval Interface1
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
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77e97e31a20c392eebae1b373bb1af53f87c23e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval-interface1"></a><span data-ttu-id="fd68c-102">ICorDebugEval Interface1</span><span class="sxs-lookup"><span data-stu-id="fd68c-102">ICorDebugEval Interface1</span></span>
<span data-ttu-id="fd68c-103">디버깅 중인 코드의 컨텍스트 내에서 디버거가 코드를 실행할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-103">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd68c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-104">Methods</span></span>  
  
|<span data-ttu-id="fd68c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-105">Method</span></span>|<span data-ttu-id="fd68c-106">설명</span><span class="sxs-lookup"><span data-stu-id="fd68c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd68c-107">Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|<span data-ttu-id="fd68c-108">이 계산을 중단 `ICorDebugEval` 개체에서 현재 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-108">Aborts the computation this `ICorDebugEval` object is currently performing.</span></span>|  
|[<span data-ttu-id="fd68c-109">CallFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-109">CallFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|<span data-ttu-id="fd68c-110">지정된 된 함수에 대 한 호출을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-110">Sets up a call to the specified function.</span></span> <span data-ttu-id="fd68c-111">(.NET Framework 버전 2.0에서에서 사용 되지 않음; 사용 하 여 [icordebugeval2:: Callparameterizedfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) 대신 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fd68c-111">(Obsolete in the .NET Framework version 2.0; use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.)</span></span>|  
|[<span data-ttu-id="fd68c-112">CreateValue 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-112">CreateValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|<span data-ttu-id="fd68c-113">초기 값이 0 또는 null 인 지정 된 형식의 "ICorDebugValue" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-113">Gets an interface pointer to an "ICorDebugValue" object of the specified type, with an initial value of zero or null.</span></span> <span data-ttu-id="fd68c-114">(.NET Framework 2.0에서 사용 되지 않음; 사용 하 여 [icordebugeval2:: Createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 대신 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fd68c-114">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.)</span></span>|  
|[<span data-ttu-id="fd68c-115">GetResult 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-115">GetResult Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|<span data-ttu-id="fd68c-116">한 인터페이스 포인터를 가져옵니다는 `ICorDebugValue` 평가의 결과가 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-116">Gets an interface pointer to an `ICorDebugValue` that contains the results of the evaluation.</span></span>|  
|[<span data-ttu-id="fd68c-117">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-117">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|<span data-ttu-id="fd68c-118">이 평가 실행 되거나 실행 될 위치는 "ICorDebugThread"에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-118">Gets an interface pointer to the "ICorDebugThread" where this evaluation is executing or will execute.</span></span>|  
|[<span data-ttu-id="fd68c-119">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-119">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|<span data-ttu-id="fd68c-120">나타내는 값을 가져옵니다 여부이 `ICorDebugEval` 개체는 현재 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-120">Gets a value that indicates whether this `ICorDebugEval` object is currently executing.</span></span>|  
|[<span data-ttu-id="fd68c-121">NewArray 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-121">NewArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|<span data-ttu-id="fd68c-122">지정한 요소 형식 및 차원에 대 한 새 배열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-122">Allocates a new array of the specified element type and dimensions.</span></span> <span data-ttu-id="fd68c-123">(.NET Framework 2.0에서 사용 되지 않음; 사용 하 여 [icordebugeval2:: Newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 대신 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fd68c-123">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.)</span></span>|  
|[<span data-ttu-id="fd68c-124">NewObject 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-124">NewObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|<span data-ttu-id="fd68c-125">새 개체 인스턴스를 할당 하 고 지정된 된 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-125">Allocates a new object instance and calls the specified constructor method.</span></span> <span data-ttu-id="fd68c-126">(.NET Framework 2.0에서 사용 되지 않음; 사용 하 여 [icordebugeval2:: Newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) 대신 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fd68c-126">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.)</span></span>|  
|[<span data-ttu-id="fd68c-127">NewObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-127">NewObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|<span data-ttu-id="fd68c-128">생성자 메서드를 호출 하지 않고 지정 된 형식의 새 개체 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-128">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span> <span data-ttu-id="fd68c-129">(.NET Framework 2.0에서 사용 되지 않음; 사용 하 여 [icordebugeval2:: Newparameterizedobjectnoconstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) 대신 합니다.)</span><span class="sxs-lookup"><span data-stu-id="fd68c-129">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.)</span></span>|  
|[<span data-ttu-id="fd68c-130">NewString 메서드</span><span class="sxs-lookup"><span data-stu-id="fd68c-130">NewString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|<span data-ttu-id="fd68c-131">지정 된 내용으로를 새 string 개체를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-131">Allocates a new string object with the specified contents.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd68c-132">설명</span><span class="sxs-lookup"><span data-stu-id="fd68c-132">Remarks</span></span>  
 <span data-ttu-id="fd68c-133">`ICorDebugEval` 확인을 수행 하는 데 사용 되는 특정 스레드 컨텍스트에서 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-133">An `ICorDebugEval` object is created in the context of a specific thread that is used to perform the evaluations.</span></span> <span data-ttu-id="fd68c-134">동일한 응용 프로그램 도메인 내 모든 개체 및 특정된 확인에 사용 되는 형식에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-134">All objects and types used in a given evaluation must reside within the same application domain.</span></span> <span data-ttu-id="fd68c-135">해당 응용 프로그램 도메인 필요한 스레드의 현재 응용 프로그램 도메인과 동일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-135">That application domain need not be the same as the current application domain of the thread.</span></span> <span data-ttu-id="fd68c-136">평가 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-136">Evaluations can be nested.</span></span>  
  
 <span data-ttu-id="fd68c-137">디버거 호출할 때까지 평가 작업을 완료 하지 않아도 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), 그러면를 수신 하 고는 [icordebugmanagedcallback:: Evalcomplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-137">The evaluation's operations do not complete until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), and then receives an [ICorDebugManagedCallback::EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) callback.</span></span> <span data-ttu-id="fd68c-138">다른 스레드가 실행을 허용 하지 않고 계산 기능을 사용 하려면 필요한 경우 스레드 중 하나를 사용 하 여 일시 중단 [icordebugcontroller:: Setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) 또는 [icordebugcontroller:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)호출 하기 전에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-138">If you need to use the evaluation functionality without allowing other threads to run, suspend the threads by using either [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) or [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
 <span data-ttu-id="fd68c-139">평가 진행 중일 때 사용자 코드가 실행 되 고, 때문에 모든 디버그 이벤트가 클래스 로드 및 중단점을 포함 하 여 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-139">Because user code is running when the evaluation is in progress, any debug events can occur, including class loads and breakpoints.</span></span> <span data-ttu-id="fd68c-140">디버거 콜백을 이러한 이벤트에 대 한 정상적으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-140">The debugger will receive callbacks, as normal, for these events.</span></span> <span data-ttu-id="fd68c-141">평가의 상태는 정상적인 프로그램 상태 검사의 일환으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-141">The state of the evaluation will be seen as part of the inspection of the normal program state.</span></span> <span data-ttu-id="fd68c-142">스택 체인 됩니다는 `CHAIN_FUNC_EVAL` 체인 ("CorDebugStepReason" 열거형을 참조 및 [icordebugchain:: Getreason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) 메서드).</span><span class="sxs-lookup"><span data-stu-id="fd68c-142">The stack chain will be a `CHAIN_FUNC_EVAL` chain (see the "CorDebugStepReason" enumeration and the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method).</span></span> <span data-ttu-id="fd68c-143">전체 디버거 API는 계속 정상적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-143">The full debugger API will continue to operate as normal.</span></span>  
  
 <span data-ttu-id="fd68c-144">교착 상태 또는 무한 루프 상황이 발생 하는 경우 사용자 코드가 완료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-144">If a deadlocked or infinite looping situation arises, the user code may never complete.</span></span> <span data-ttu-id="fd68c-145">이 경우 호출 해야 [icordebugeval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) 프로그램을 다시 시작 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="fd68c-145">In such a case, you must call [ICorDebugEval::Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) before resuming the program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd68c-146">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-146">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd68c-147">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd68c-147">Requirements</span></span>  
 <span data-ttu-id="fd68c-148">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd68c-148">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd68c-149">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd68c-149">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd68c-150">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd68c-150">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd68c-151">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd68c-151">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd68c-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd68c-152">See Also</span></span>  
    
    
    
 [<span data-ttu-id="fd68c-153">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd68c-153">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
