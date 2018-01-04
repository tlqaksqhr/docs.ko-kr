---
title: "ICorProfilerCallback::RuntimeSuspendAborted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendAborted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d62df6fc90a2601997aeb7ecbe410f1a35d7012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="a0973-102">ICorProfilerCallback::RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="a0973-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="a0973-103">런타임에 발생 하는 런타임 일시 중단가 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a0973-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0973-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0973-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a0973-105">설명</span><span class="sxs-lookup"><span data-stu-id="a0973-105">Remarks</span></span>  
 <span data-ttu-id="a0973-106">두 스레드는 런타임을 일시 중단 하려고 동시에 실행 시 일시 중단 취소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0973-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="a0973-107">중 하나는 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 콜백 또는 `RuntimeSuspendAborted` 콜백 단일 스레드 다음에 발생 합니다는 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="a0973-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="a0973-108">`RuntimeSuspendAborted` callback은 동일한 스레드에서 발생 하는 `RuntimeSuspendStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0973-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0973-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0973-109">Requirements</span></span>  
 <span data-ttu-id="a0973-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0973-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0973-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0973-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0973-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0973-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0973-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0973-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0973-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0973-114">See Also</span></span>  
 [<span data-ttu-id="a0973-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0973-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
