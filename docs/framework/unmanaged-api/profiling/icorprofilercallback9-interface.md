---
title: ICorProfilerCallback9 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452379"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="48681-102">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48681-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="48681-103">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="48681-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="48681-104">서브 클래스 [ICorProfilerCallback8](icorprofilercallback8-interface.md) 동적 메서드가 가비지 수집 되 고 이후에 언로드 되었음을 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 되는 콜백 메서드를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="48681-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48681-105">메서드</span><span class="sxs-lookup"><span data-stu-id="48681-105">Methods</span></span>  
  
|<span data-ttu-id="48681-106">메서드</span><span class="sxs-lookup"><span data-stu-id="48681-106">Method</span></span>|<span data-ttu-id="48681-107">설명</span><span class="sxs-lookup"><span data-stu-id="48681-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48681-108">DynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="48681-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="48681-109">동적 메서드가 가비지 수집 되 고 이후에 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="48681-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48681-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48681-110">Requirements</span></span>  
 <span data-ttu-id="48681-111">**플랫폼:** 참조 [시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48681-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48681-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48681-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="48681-113">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="48681-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="48681-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48681-114">See Also</span></span>  
<span data-ttu-id="48681-115">[프로 파일링 인터페이스](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="48681-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="48681-116">[ICorProfilerCallback8 인터페이스](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="48681-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="48681-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted 메서드](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="48681-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="48681-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="48681-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
