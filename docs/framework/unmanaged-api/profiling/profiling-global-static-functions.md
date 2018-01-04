---
title: "프로파일링 전역 정적 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66f22557dd6020ff5040d5aaf76cb12e9ae9965c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="9d239-102">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-102">Profiling Global Static Functions</span></span>
<span data-ttu-id="9d239-103">이 섹션에서는 프로 파일링 API를 사용 하는 관리 되지 않는 API 함수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d239-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9d239-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="9d239-105">.NET framework 버전 1 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-105">.NET Framework version 1 Profiling Functions</span></span>  
 [<span data-ttu-id="9d239-106">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-106">FunctionEnter Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 <span data-ttu-id="9d239-107">제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="9d239-108">.NET Framework 2.0의에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="9d239-109">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-109">FunctionLeave Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 <span data-ttu-id="9d239-110">호출자에 게 반환 하는 함수 인지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="9d239-111">.NET Framework 2.0의에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="9d239-112">FunctionTailcall 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-112">FunctionTailcall Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 <span data-ttu-id="9d239-113">다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="9d239-114">.NET Framework 2.0의에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="9d239-115">.NET framework 버전 2 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-115">.NET Framework version 2 Profiling Functions</span></span>  
 [<span data-ttu-id="9d239-116">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-116">FunctionIDMapper Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 <span data-ttu-id="9d239-117">지정 된 식별자는 함수에 사용할 대체 ID에 다시 매핑할 수는 프로파일러에 알립니다.는 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), 및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 해당 함수에 대 한 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="9d239-118">또한 프로파일러를를 해당 함수에 대 한 콜백을 받을지 여부를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="9d239-119">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-119">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 <span data-ttu-id="9d239-120">제어는 함수에 전달 되는 및 프레임 및 함수 인수는 스택에 대 한 정보를 제공 합니다. 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="9d239-121">사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-121">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="9d239-122">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-122">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 <span data-ttu-id="9d239-123">함수는 호출자에 반환 하 고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="9d239-124">사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-124">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="9d239-125">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-125">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 <span data-ttu-id="9d239-126">현재 실행 중인 함수를 다른 함수에 대 한 마무리 호출이 수행 하려고 하 고 스택 프레임에 대 한 정보를 제공 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="9d239-127">사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-127">Deprecated in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
 [<span data-ttu-id="9d239-128">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-128">StackSnapshotCallback Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 <span data-ttu-id="9d239-129">프로파일러 동안 시작 되는 스택 워크가 스택의 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보 제공의 [icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d239-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="9d239-130">.NET framework 버전 4 프로 파일링 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-130">.NET Framework version 4 Profiling Functions</span></span>  
 [<span data-ttu-id="9d239-131">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-131">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 <span data-ttu-id="9d239-132">지정 된 식별자는 함수에 사용할 대체 ID에 다시 매핑할 수는 프로파일러에 알립니다.는 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), 또는[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), 및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 해당 함수에 대 한 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="9d239-133">또한 프로파일러를를 해당 함수에 대 한 콜백을 받을지 여부를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="9d239-134">`FunctionIDMapper2`확장은 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 작동는 `clientData` 프로파일러는 런타임 중 명확히 구분 하기 사용할 수 있는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-134">`FunctionIDMapper2` extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="9d239-135">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-135">FunctionEnter3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 <span data-ttu-id="9d239-136">제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="9d239-137">FunctionEnter3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-137">FunctionEnter3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 <span data-ttu-id="9d239-138">에 전달 될 수 있는 핸들을 제공 및 제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다. [icorprofilerinfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 스택 프레임 및 함수 인수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="9d239-139">FunctionLeave3 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-139">FunctionLeave3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 <span data-ttu-id="9d239-140">제어는 함수에서 반환 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="9d239-141">FunctionLeave3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-141">FunctionLeave3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 <span data-ttu-id="9d239-142">에 전달 될 수 있는 핸들을 제공 하 고 제어는 함수에서 반환 되는 프로파일러에 알립니다 [icorprofilerinfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 스택 프레임 및 반환 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="9d239-143">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-143">FunctionTailcall3 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 <span data-ttu-id="9d239-144">다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="9d239-145">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9d239-145">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 <span data-ttu-id="9d239-146">에 전달 될 수 있는 핸들을 제공 하 고 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출이 수행 하려고 하는 프로파일러에 알립니다 [icorprofilerinfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) 스택 프레임을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d239-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9d239-147">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9d239-147">Related Sections</span></span>  
 [<span data-ttu-id="9d239-148">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="9d239-148">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="9d239-149">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d239-149">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="9d239-150">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="9d239-150">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="9d239-151">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="9d239-151">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
