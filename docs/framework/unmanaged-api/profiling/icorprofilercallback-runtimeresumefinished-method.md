---
title: ICorProfilerCallback::RuntimeResumeFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6b983db7da258fb94f941d01914ece0f7b1359f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453309"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="9b6e0-102">ICorProfilerCallback::RuntimeResumeFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="9b6e0-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="9b6e0-103">런타임에 모든 런타임 스레드 왔음 및 정상 작동 상태로 반환 되었습니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9b6e0-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b6e0-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9b6e0-105">설명</span><span class="sxs-lookup"><span data-stu-id="9b6e0-105">Remarks</span></span>  
 <span data-ttu-id="9b6e0-106">`RuntimeResumeFinished` 콜백와 동일한 스레드에서 발생 하도록 보장 하지는 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b6e0-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="9b6e0-107">하지만와 동일한 스레드에서 발생 하도록 보장는 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b6e0-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b6e0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b6e0-108">Requirements</span></span>  
 <span data-ttu-id="9b6e0-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b6e0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b6e0-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b6e0-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b6e0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b6e0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b6e0-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b6e0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6e0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b6e0-113">See Also</span></span>  
 [<span data-ttu-id="9b6e0-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b6e0-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
