---
title: ICorProfilerCallback8 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455285"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="6c55e-102">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c55e-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="6c55e-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="6c55e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="6c55e-104">서브 클래스 [ICorProfilerCallback7](icorprofilercallback7-interface.md) 동적 메서드의 JIT 컴파일 시작 되 고 완료 하는 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 되는 콜백 메서드를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c55e-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="6c55e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6c55e-105">Methods</span></span>  
  
|<span data-ttu-id="6c55e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6c55e-106">Method</span></span>|<span data-ttu-id="6c55e-107">설명</span><span class="sxs-lookup"><span data-stu-id="6c55e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c55e-108">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="6c55e-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="6c55e-109">동적 메서드의 JIT 컴파일이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6c55e-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="6c55e-110">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="6c55e-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="6c55e-111">동적 메서드의 JIT 컴파일 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6c55e-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c55e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c55e-112">Requirements</span></span>  
 <span data-ttu-id="6c55e-113">**플랫폼:** 참조 [시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c55e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c55e-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c55e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="6c55e-115">**.NET framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c55e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c55e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c55e-116">See Also</span></span>  
<span data-ttu-id="6c55e-117">[프로 파일링 인터페이스](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="6c55e-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="6c55e-118">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c55e-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
