---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce413ba184cfec731c6bac0d7f561c345bf53181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452012"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="e72b4-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="e72b4-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="e72b4-103">예외의 해제 단계 처리 없어진 프로파일러에 알립니다는 `finally` 절.</span><span class="sxs-lookup"><span data-stu-id="e72b4-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e72b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="e72b4-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e72b4-105">설명</span><span class="sxs-lookup"><span data-stu-id="e72b4-105">Remarks</span></span>  
 <span data-ttu-id="e72b4-106">프로파일러 스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 호출 하는 동안 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e72b4-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e72b4-107">이때 프로파일러가 차단 및 가비지 수집을 시도 하는 경우 런타임에서이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e72b4-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e72b4-108">또한이 호출 하는 동안 프로파일러 호출 해서는 안 관리 코드에 또는 관리 되는 메모리 할당에서.</span><span class="sxs-lookup"><span data-stu-id="e72b4-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e72b4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e72b4-109">Requirements</span></span>  
 <span data-ttu-id="e72b4-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e72b4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e72b4-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e72b4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e72b4-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e72b4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e72b4-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e72b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e72b4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e72b4-114">See Also</span></span>  
 [<span data-ttu-id="e72b4-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e72b4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e72b4-116">ExceptionUnwindFinallyEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="e72b4-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
