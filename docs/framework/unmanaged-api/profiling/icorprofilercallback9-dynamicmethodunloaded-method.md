---
title: ICorProfilerCallback9::DynamicMethodUnloaded 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452405"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="726c1-102">ICorProfilerCallback9::DynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="726c1-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="726c1-103">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="726c1-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="726c1-104">동적 메서드는 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="726c1-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="726c1-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="726c1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="726c1-106">Parameters</span></span>  
<span data-ttu-id="726c1-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="726c1-107">[in] `functionId`</span></span>  
<span data-ttu-id="726c1-108">가비지 수집 되 고 언로드된 된 메모리에서 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="726c1-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="726c1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="726c1-109">Requirements</span></span>  
 <span data-ttu-id="726c1-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="726c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726c1-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="726c1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="726c1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="726c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="726c1-113">**.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="726c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726c1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="726c1-114">See Also</span></span>  
[<span data-ttu-id="726c1-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="726c1-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="726c1-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="726c1-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="726c1-117">[ICorProfilerCallback9 인터페이스](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="726c1-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="726c1-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="726c1-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
