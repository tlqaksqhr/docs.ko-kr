---
title: "ICorProfilerCallback2::FinalizeableObjectQueued 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.FinalizeableObjectQueued
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ed9c66f7d588d855daa550031c832810b914d49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="f695a-102">ICorProfilerCallback2::FinalizeableObjectQueued 메서드</span><span class="sxs-lookup"><span data-stu-id="f695a-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="f695a-103">종료자 스레드는 실행할 수 있도록 종료자 인 개체가 이미 대기열 코드 프로파일러에 알립니다. 해당 `Finalize` 메서드.</span><span class="sxs-lookup"><span data-stu-id="f695a-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f695a-104">구문</span><span class="sxs-lookup"><span data-stu-id="f695a-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f695a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f695a-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="f695a-106">[in] 값은 [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) 종료자의 측면을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="f695a-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="f695a-107">[in] 큐에 대기 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f695a-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f695a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f695a-108">Requirements</span></span>  
 <span data-ttu-id="f695a-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f695a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f695a-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f695a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f695a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f695a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f695a-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f695a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f695a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f695a-113">See Also</span></span>  
 [<span data-ttu-id="f695a-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f695a-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f695a-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f695a-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
