---
title: ICorProfilerCallback::ThreadDestroyed 메서드
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4929d9aaf7de9af72ec5ba93f5d7e35c712ac6cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451703"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="df7dc-102">ICorProfilerCallback::ThreadDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="df7dc-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="df7dc-103">스레드가 제거 된 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="df7dc-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="df7dc-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df7dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df7dc-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="df7dc-106">[in] 소멸 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="df7dc-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df7dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="df7dc-107">Remarks</span></span>  
 <span data-ttu-id="df7dc-108">`threadId` 이 호출 시 값이 유효한 더 이상.</span><span class="sxs-lookup"><span data-stu-id="df7dc-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7dc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df7dc-109">Requirements</span></span>  
 <span data-ttu-id="df7dc-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7dc-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df7dc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df7dc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df7dc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df7dc-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7dc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df7dc-114">See Also</span></span>  
 [<span data-ttu-id="df7dc-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df7dc-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="df7dc-116">ThreadCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="df7dc-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
