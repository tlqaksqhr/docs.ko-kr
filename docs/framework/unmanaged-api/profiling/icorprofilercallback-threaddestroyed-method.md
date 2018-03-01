---
title: "ICorProfilerCallback::ThreadDestroyed 메서드"
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
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 419a8a0797761429f41f7472d812aaebdbbf706c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="20476-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="20476-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="20476-103">스레드가 제거 된 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="20476-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20476-104">구문</span><span class="sxs-lookup"><span data-stu-id="20476-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20476-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20476-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="20476-106">[in] 소멸 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20476-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20476-107">설명</span><span class="sxs-lookup"><span data-stu-id="20476-107">Remarks</span></span>  
 <span data-ttu-id="20476-108">`threadId` 이 호출 시 값이 유효한 더 이상.</span><span class="sxs-lookup"><span data-stu-id="20476-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20476-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20476-109">Requirements</span></span>  
 <span data-ttu-id="20476-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20476-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20476-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20476-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20476-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20476-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20476-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20476-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20476-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20476-114">See Also</span></span>  
 [<span data-ttu-id="20476-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20476-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="20476-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="20476-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
