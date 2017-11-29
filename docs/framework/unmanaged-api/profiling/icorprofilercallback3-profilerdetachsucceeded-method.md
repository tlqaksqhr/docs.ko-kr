---
title: "ICorProfilerCallback3::ProfilerDetachSucceeded 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4413e5c475bce6d6f2eea1f7a968c946237f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="f2ada-102">ICorProfilerCallback3::ProfilerDetachSucceeded 메서드</span><span class="sxs-lookup"><span data-stu-id="f2ada-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="f2ada-103">CLR(공용 언어 런타임)이 프로파일러 DLL을 언로드한다고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ada-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2ada-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f2ada-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f2ada-105">Return Value</span></span>  
 <span data-ttu-id="f2ada-106">이 콜백의 반환 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ada-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2ada-107">Remarks</span></span>  
 <span data-ttu-id="f2ada-108">`ProfilerDetachSucceeded` 콜백은 모든 스레드가 프로파일러의 코드를 종료한 후에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="f2ada-109">이 메서드가 호출되면 프로파일러는 UI 또는 로깅 구성 요소에 알림과 같은 소멸자에 적합하지 않은 마지막 작업을 모두 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="f2ada-110">그러나 프로파일러 해야 함수를 호출 하지이 콜백 중 CLR에서 제공 되는 인터페이스에 (예:는 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 또는 `IMetaData*` 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="f2ada-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="f2ada-111">CLR은 Windows 응용 프로그램 이벤트 로그에 항목을 만들어 분리 작업에 성공했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="f2ada-112">프로파일러가 이 콜백에서 반환된 후 CLR은 프로파일러 개체를 해제하고 프로파일러 DLL을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="f2ada-113">따라서 프로파일러는 이 콜백에서 반환된 후 프로파일러 DLL 내에서 실행되는 작업을 수행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="f2ada-114">예를 들어 스레드를 만들거나 타이머 콜백을 등록하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ada-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2ada-115">Requirements</span></span>  
 <span data-ttu-id="f2ada-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ada-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ada-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2ada-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2ada-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ada-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ada-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ada-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ada-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ada-120">See Also</span></span>  
 [<span data-ttu-id="f2ada-121">메타 데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2ada-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="f2ada-122">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2ada-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="f2ada-123">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2ada-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f2ada-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f2ada-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
