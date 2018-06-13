---
title: ICorProfilerCallback4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bcddc143cacc3df016e6b8dd7907a67354c4311
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455744"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="3f865-102">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f865-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="3f865-103">공용 언어 런타임 (CLR) 사용 하 여 프로파일러에 정보를 통신 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f865-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-104">Methods</span></span>  
  
|<span data-ttu-id="3f865-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-105">Method</span></span>|<span data-ttu-id="3f865-106">설명</span><span class="sxs-lookup"><span data-stu-id="3f865-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f865-107">GetReJITParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="3f865-108">새 다시 컴파일된 메서드 본문에 대 한 대체 코드 생성 플래그를 설정 하려면 코드 프로파일러를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="3f865-109">MovedReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="3f865-110">압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="3f865-111">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="3f865-112">적시에 (JIT) 컴파일러는 함수는 다시 컴파일은 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="3f865-113">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="3f865-114">적시에 (JIT) 컴파일러는 함수를 다시 시작 했습니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="3f865-115">ReJITError 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="3f865-116">다시 컴파일한 요청을 처리 하는 동안 발생 한 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="3f865-117">SurvivingReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="3f865-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="3f865-118">비압축 가비지 컬렉션의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f865-119">설명</span><span class="sxs-lookup"><span data-stu-id="3f865-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f865-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f865-120">Requirements</span></span>  
 <span data-ttu-id="3f865-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f865-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f865-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f865-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f865-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f865-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f865-124">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f865-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f865-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f865-125">See Also</span></span>  
 [<span data-ttu-id="3f865-126">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f865-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="3f865-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f865-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="3f865-128">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f865-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
