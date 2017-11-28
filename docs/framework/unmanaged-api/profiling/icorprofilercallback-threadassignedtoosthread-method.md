---
title: "ICorProfilerCallback::ThreadAssignedToOSThread 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadAssignedToOSThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c70de2b53fd428361d5404aa406d2b2be67d0914
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="5a2f9-102">ICorProfilerCallback::ThreadAssignedToOSThread 메서드</span><span class="sxs-lookup"><span data-stu-id="5a2f9-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="5a2f9-103">관리 되는 스레드는 특정 운영 체제 스레드를 사용 하 여 구현 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f9-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a2f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a2f9-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a2f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a2f9-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="5a2f9-106">[in] 관리 되는 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f9-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="5a2f9-107">[in] 운영 체제 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f9-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a2f9-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a2f9-108">Remarks</span></span>  
 <span data-ttu-id="5a2f9-109">`ThreadAssignedToOSThread` 프로파일러 파이버 관리 되는 스레드는 운영 체제 스레드 간에 정확한 매핑을 유지할 수 있도록 콜백 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f9-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a2f9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a2f9-110">Requirements</span></span>  
 <span data-ttu-id="5a2f9-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a2f9-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a2f9-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a2f9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a2f9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a2f9-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a2f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2f9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a2f9-115">See Also</span></span>  
 [<span data-ttu-id="5a2f9-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a2f9-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
