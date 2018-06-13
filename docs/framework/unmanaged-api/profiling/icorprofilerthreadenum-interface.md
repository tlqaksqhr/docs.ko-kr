---
title: ICorProfilerThreadEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b9662ccb854345d41bb73a5cf01a94b9949891d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457197"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="b5dba-102">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5dba-102">ICorProfilerThreadEnum Interface</span></span>
<span data-ttu-id="b5dba-103">공용 언어 런타임에서 스레드 컬렉션을 순차적으로 반복하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-103">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5dba-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-104">Methods</span></span>  
  
|<span data-ttu-id="b5dba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-105">Method</span></span>|<span data-ttu-id="b5dba-106">설명</span><span class="sxs-lookup"><span data-stu-id="b5dba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5dba-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="b5dba-108">이 `ICorProfilerThreadEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-108">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="b5dba-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="b5dba-110">응용 프로그램에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-110">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="b5dba-111">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-next-method.md)|<span data-ttu-id="b5dba-112">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 스레드 컬렉션에서 지정된 개수의 연속 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-112">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="b5dba-113">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="b5dba-114">열거자의 커서를 시퀀스의 시작 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="b5dba-115">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="b5dba-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="b5dba-116">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-116">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5dba-117">설명</span><span class="sxs-lookup"><span data-stu-id="b5dba-117">Remarks</span></span>  
 <span data-ttu-id="b5dba-118">`ICorProfilerThreadEnum` 인터페이스는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-118">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="b5dba-119">배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="b5dba-120">즉, 수신기가 배열 요소의 흐름을 명시적으로 제어하여 대형 배열을 메서드 매개 변수로 전달하는 기능과 관련된 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5dba-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5dba-121">Requirements</span></span>  
 <span data-ttu-id="b5dba-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5dba-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5dba-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5dba-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5dba-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5dba-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5dba-125">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5dba-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5dba-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5dba-126">See Also</span></span>  
 [<span data-ttu-id="b5dba-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5dba-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="b5dba-128">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5dba-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
