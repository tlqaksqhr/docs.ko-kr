---
title: ICorProfilerCallback::RuntimeThreadResumed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f971c5175307c1e1df6890c136b306860e54d23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452711"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="a59db-102">ICorProfilerCallback::RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="a59db-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="a59db-103">지정된 된 스레드가 일시 중단 된 후 다시 시작 했습니다을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a59db-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59db-104">구문</span><span class="sxs-lookup"><span data-stu-id="a59db-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a59db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a59db-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a59db-106">[in] 다시 시작 되었으므로 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a59db-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a59db-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a59db-107">Requirements</span></span>  
 <span data-ttu-id="a59db-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a59db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a59db-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a59db-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a59db-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a59db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a59db-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a59db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59db-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a59db-112">See Also</span></span>  
 [<span data-ttu-id="a59db-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a59db-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a59db-114">RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="a59db-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
