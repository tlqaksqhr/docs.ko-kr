---
title: "ICorProfilerCallback::RuntimeThreadResumed 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadResumed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94d7e46140b36d6fcce788d70cc856a6776e9f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="92000-102">ICorProfilerCallback::RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="92000-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="92000-103">지정된 된 스레드가 일시 중단 된 후 다시 시작 했습니다을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="92000-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92000-104">구문</span><span class="sxs-lookup"><span data-stu-id="92000-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92000-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92000-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="92000-106">[in] 다시 시작 되었으므로 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="92000-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92000-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92000-107">Requirements</span></span>  
 <span data-ttu-id="92000-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92000-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92000-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92000-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92000-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92000-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92000-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92000-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92000-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92000-112">See Also</span></span>  
 [<span data-ttu-id="92000-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92000-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="92000-114">RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="92000-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
