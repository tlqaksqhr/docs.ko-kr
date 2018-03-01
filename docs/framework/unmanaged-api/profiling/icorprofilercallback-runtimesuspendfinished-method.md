---
title: "ICorProfilerCallback::RuntimeSuspendFinished 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6127d0c5f3b193dad1586cdaf92beb8d8734376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="e7545-102">ICorProfilerCallback::RuntimeSuspendFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="e7545-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="e7545-103">런타임에 모든 런타임 스레드의 일시 중단이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7545-104">구문</span><span class="sxs-lookup"><span data-stu-id="e7545-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e7545-105">설명</span><span class="sxs-lookup"><span data-stu-id="e7545-105">Remarks</span></span>  
 <span data-ttu-id="e7545-106">비관리 코드에 있는 모든 런타임 스레드 다시 런타임에 입력 하려고 시도할 때까지 실행을 계속 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="e7545-107">해당 시점 것도 일시 중단 됩니다 런타임 재개할 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="e7545-108">런타임에 입력 하는 새 스레드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="e7545-109">런타임에서 모든 스레드는 인터럽트 가능한 코드에 이미 또는 인터럽트 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 되는 경우 즉시 하거나 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="e7545-110">`RuntimeSuspendFinished` callback은 동일한 스레드에서 발생 하는 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7545-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7545-111">Requirements</span></span>  
 <span data-ttu-id="e7545-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7545-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7545-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7545-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7545-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7545-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7545-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7545-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7545-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7545-116">See Also</span></span>  
 [<span data-ttu-id="e7545-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7545-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e7545-118">RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="e7545-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
