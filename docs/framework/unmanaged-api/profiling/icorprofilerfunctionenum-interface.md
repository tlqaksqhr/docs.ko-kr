---
title: "ICorProfilerFunctionEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum
helpviewer_keywords: ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1067fa6738b23492b3a58500b4cb6ba1d030304f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="58186-102">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58186-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="58186-103">공용 언어 런타임에서 함수 컬렉션을 순차적으로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58186-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58186-104">메서드</span><span class="sxs-lookup"><span data-stu-id="58186-104">Methods</span></span>  
  
|<span data-ttu-id="58186-105">메서드</span><span class="sxs-lookup"><span data-stu-id="58186-105">Method</span></span>|<span data-ttu-id="58186-106">설명</span><span class="sxs-lookup"><span data-stu-id="58186-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58186-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="58186-108">이 `ICorProfilerFunctionEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58186-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="58186-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="58186-110">응용 프로그램에서 로드했거나 프로파일러에서 강제로 로드한 함수 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58186-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="58186-111">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="58186-112">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 함수 컬렉션에서 지정된 개수의 연속 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58186-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="58186-113">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="58186-114">열거자의 커서를 시퀀스의 시작 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="58186-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="58186-115">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="58186-116">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="58186-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58186-117">설명</span><span class="sxs-lookup"><span data-stu-id="58186-117">Remarks</span></span>  
 <span data-ttu-id="58186-118">`ICorProfilerFunctionEnum` 인터페이스는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="58186-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="58186-119">배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="58186-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="58186-120">즉, 수신기가 배열 요소의 흐름을 명시적으로 제어하여 대형 배열을 메서드 매개 변수로 전달하는 기능과 관련된 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58186-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="58186-121">`ICorProfilerFunctionEnum`은 이미 JIT 컴파일된 함수를 열거하지만 Ngen.exe로 생성된 네이티브 이미지에서 로드된 함수는 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58186-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58186-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58186-122">Requirements</span></span>  
 <span data-ttu-id="58186-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58186-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58186-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58186-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58186-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58186-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58186-126">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58186-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58186-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58186-127">See Also</span></span>  
 [<span data-ttu-id="58186-128">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58186-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="58186-129">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58186-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="58186-130">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="58186-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
