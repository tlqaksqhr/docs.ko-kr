---
title: ICorDebugStepper Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266e8c664ac7c5efa1b199efc522f0b890e38e3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="b5109-102">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="b5109-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="b5109-103">디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5109-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-104">Methods</span></span>  
  
|<span data-ttu-id="b5109-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-105">Method</span></span>|<span data-ttu-id="b5109-106">설명</span><span class="sxs-lookup"><span data-stu-id="b5109-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5109-107">Deactivate 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="b5109-108">이 인해 `ICorDebugStepper` 받은 마지막 단계 명령 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="b5109-109">IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="b5109-110">나타내는 값을 가져옵니다 여부이 `ICorDebugStepper` 현재 단계를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="b5109-111">SetInterceptMask 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="b5109-112">한 단계씩 코드의 형식을 지정 하는 CorDebugIntercept 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="b5109-113">SetRangeIL 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="b5109-114">나타내는 값을 설정 여부에 대 한 호출이 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 네이티브 코드에 상대적인 또는 단계별로 중인 메서드의 MSIL (intermediate language) 코드를 Microsoft에 인수 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="b5109-115">SetUnmappedStopMask 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="b5109-116">매핑되지 않은 코드 실행을 중지할의 유형을 지정 하는 CorDebugUnmappedStop 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="b5109-117">Step 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="b5109-118">이 인해 `ICorDebugStepper` 포함 스레드를 통해 및 필요에 따라을 단일 단계를 한 단계씩 스레드 내에서 호출 된 함수를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="b5109-119">StepOut 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="b5109-120">이 인해 `ICorDebugStepper` 호출 프레임을 현재 프레임 제어 반환 포함 스레드를 통해 단일 단계를 때 완료를 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="b5109-121">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="b5109-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="b5109-122">이 인해 `ICorDebugStepper` 이후의 지정된 된 범위의 코드에 도달할 때 반환 되도록 하 고 포함 스레드를 통해 단일 단계로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5109-123">설명</span><span class="sxs-lookup"><span data-stu-id="b5109-123">Remarks</span></span>  
 <span data-ttu-id="b5109-124">`ICorDebugStepper` 인터페이스는 다음 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="b5109-125">발급 된 단계 명령이 해당 명령의 완료 사이의 식별자로 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="b5109-126">수행할 수 있는 모든 단계별 실행을 캡슐화 하는 중앙 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="b5109-127">중간 단계별 실행 작업을 취소 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="b5109-128">스레드당 둘 이상의 스텝 퍼 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="b5109-129">예를 들어 함수를 프로시저 단위로 실행 하는 동안 중단점에 도달할 수 있습니다 및 사용자를 해당 함수 내에서 새 단계별 실행 작업을 시작 하려는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="b5109-130">이 상황을 처리 하는 방법을 결정 하기 위해 디버거는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="b5109-131">디버거 원래 단계별 실행 작업을 취소 하거나 두 작업을 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="b5109-132">`ICorDebugStepper` 인터페이스 둘 다 선택한 항목을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="b5109-133">공용 언어 런타임 (CLR)에서는 마샬링된 크로스 스레드 호출 하는 경우 스레드 간에 스텝 마이그레이션될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5109-134">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5109-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5109-135">Requirements</span></span>  
 <span data-ttu-id="b5109-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5109-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5109-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5109-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5109-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5109-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5109-139">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5109-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5109-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5109-140">See Also</span></span>  
 [<span data-ttu-id="b5109-141">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5109-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
