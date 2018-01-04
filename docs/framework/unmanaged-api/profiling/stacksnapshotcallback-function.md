---
title: "StackSnapshotCallback 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackSnapshotCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: StackSnapshotCallback
helpviewer_keywords: StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32cf21fb5a76fdec4daa322d53a8eb218ae2f2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="b7a50-102">StackSnapshotCallback 함수</span><span class="sxs-lookup"><span data-stu-id="b7a50-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="b7a50-103">프로파일러 동안 시작 되는 스택 워크가 스택의 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보 제공의 [icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b7a50-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a50-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7a50-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7a50-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7a50-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="b7a50-106">[in] 관리 되지 않는 프레임에 대 한 실행에 대 한이 콜백에서이 값이 0 인 경우 그렇지 않은 경우 관리 되는 함수 식별자 이며이 콜백에서 관리 되는 프레임에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="b7a50-107">[in] 프레임에서 네이티브 코드의 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="b7a50-108">[in] A `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="b7a50-109">이 값은이 콜백 하는 동안에 사용 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b7a50-110">[in] 크기는 `CONTEXT` 에서 참조 하는 구조는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="b7a50-111">[in] Win32에 대 한 포인터 `CONTEXT` 이 프레임에 대 한 CPU의 상태를 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="b7a50-112">`context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그에 전달 된 경우에 유효 `ICorProfilerInfo2::DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="b7a50-113">[in] 직접 전달 되는 클라이언트 데이터에 대 한 포인터 `ICorProfilerInfo2::DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7a50-114">설명</span><span class="sxs-lookup"><span data-stu-id="b7a50-114">Remarks</span></span>  
 <span data-ttu-id="b7a50-115">`StackSnapshotCallback` 프로파일러 작성자 함수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="b7a50-116">수행 된 작업의 복잡성을 제한 해야 `StackSnapshotCallback`합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="b7a50-117">예를 들어, 사용 하는 경우 `ICorProfilerInfo2::DoStackSnapshot` 비동기 방식으로, 대상 스레드가 있습니다 잠금을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="b7a50-118">경우 내의 코드에서 `StackSnapshotCallback` 같은 잠금이 필요한 교착 상태가 발생 하지 못한다면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="b7a50-119">`ICorProfilerInfo2::DoStackSnapshot` 메서드 호출에서 `StackSnapshotCallback` 관리 되는 프레임에 한 번씩 또는 관리 되지 않는 프레임이 실행 당 한 번 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="b7a50-120">경우 `StackSnapshotCallback` 라고 관리 되지 않는 프레임을 실행 하는 프로파일러 레지스터 컨텍스트로 사용 될 수 있습니다 (으로 참조 되는 `context` 매개 변수) 자체 관리 되지 않는 스택 워크를 수행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="b7a50-121">이 경우 Win32 `CONTEXT` 구조 관리 되지 않는 프레임이 실행 되는 가장 최근에 푸시된 프레임에 대 한 CPU 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="b7a50-122">하지만 Win32 `CONTEXT` 모든 레지스터에 대 한 값을 포함 하는 구조, 스택 포인터 레지스터, 프레임 포인터 레지스터, 명령 포인터 레지스터 (보존)이 표시 되는 비휘발성의 값만 사용 해야 정수 레지스터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a50-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7a50-123">Requirements</span></span>  
 <span data-ttu-id="b7a50-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a50-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a50-125">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b7a50-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b7a50-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7a50-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7a50-127">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a50-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a50-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7a50-128">See Also</span></span>  
 [<span data-ttu-id="b7a50-129">DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="b7a50-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="b7a50-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b7a50-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
