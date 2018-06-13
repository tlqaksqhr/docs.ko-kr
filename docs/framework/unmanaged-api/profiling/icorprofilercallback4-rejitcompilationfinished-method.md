---
title: ICorProfilerCallback4::ReJITCompilationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf2e1be735150dfb006e2274c79c25649d0271d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455359"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="105de-102">ICorProfilerCallback4::ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="105de-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="105de-103">적시에 (JIT) 컴파일러는 함수를 다시 컴파일 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="105de-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105de-104">구문</span><span class="sxs-lookup"><span data-stu-id="105de-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="105de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="105de-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="105de-106">[in] 다시 컴파일 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="105de-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="105de-107">[in] JIT 다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="105de-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="105de-108">[in] JIT 다시 컴파일을 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="105de-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="105de-109">[in] `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 있는지 나타내려면 `false` 차단는 영향을 주지 않는지 런타임에 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="105de-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="105de-110">값이 `true` 런타임에 대해, 영향을 주지 않으며 하지만 프로 파일링 결과 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="105de-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="105de-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="105de-111">Requirements</span></span>  
 <span data-ttu-id="105de-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="105de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="105de-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="105de-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="105de-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="105de-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="105de-115">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="105de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105de-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="105de-116">See Also</span></span>  
 [<span data-ttu-id="105de-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="105de-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="105de-118">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="105de-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="105de-119">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="105de-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="105de-120">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="105de-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
