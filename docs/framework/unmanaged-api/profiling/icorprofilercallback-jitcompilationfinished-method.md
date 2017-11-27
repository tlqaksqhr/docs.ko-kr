---
title: "ICorProfilerCallback::JITCompilationFinished 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9719ce1474c2111692c6176655b75bd2d7edf923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="69e51-102">ICorProfilerCallback::JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="69e51-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="69e51-103">적시에 (JIT) 컴파일러가 함수 컴파일이 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e51-104">구문</span><span class="sxs-lookup"><span data-stu-id="69e51-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69e51-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69e51-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="69e51-106">[in] 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="69e51-107">[in] 컴파일의 성공 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="69e51-108">[in] 차단 여부를 나타내는 프로파일러 값 런타임의 작업에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="69e51-109">값은 `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="69e51-110">값이 있지만 `true` 런타임 나쁜 영향을 주지, 프로 파일링 결과 왜곡 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e51-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69e51-111">Requirements</span></span>  
 <span data-ttu-id="69e51-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69e51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e51-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69e51-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69e51-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e51-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e51-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69e51-116">See Also</span></span>  
 [<span data-ttu-id="69e51-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69e51-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="69e51-118">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="69e51-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
