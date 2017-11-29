---
title: "ICorProfilerCallback::ThreadCreated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b62d5d1129bb71a95ac4e98624558272b08f0683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="9c2ae-102">ICorProfilerCallback::ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="9c2ae-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="9c2ae-103">스레드는 작성 된 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9c2ae-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c2ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c2ae-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c2ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c2ae-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="9c2ae-106">[in] 생성 된 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9c2ae-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c2ae-107">설명</span><span class="sxs-lookup"><span data-stu-id="9c2ae-107">Remarks</span></span>  
 <span data-ttu-id="9c2ae-108">`threadId` 값이 즉시 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2ae-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c2ae-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c2ae-109">Requirements</span></span>  
 <span data-ttu-id="9c2ae-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c2ae-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c2ae-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c2ae-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c2ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c2ae-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c2ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2ae-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c2ae-114">See Also</span></span>  
 [<span data-ttu-id="9c2ae-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c2ae-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9c2ae-116">ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="9c2ae-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
