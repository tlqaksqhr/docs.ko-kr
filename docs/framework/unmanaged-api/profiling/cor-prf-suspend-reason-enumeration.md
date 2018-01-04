---
title: "COR_PRF_SUSPEND_REASON 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SUSPEND_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SUSPEND_REASON
helpviewer_keywords: COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="38c42-102">COR_PRF_SUSPEND_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="38c42-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="38c42-103">런타임이 일시 중단 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c42-104">구문</span><span class="sxs-lookup"><span data-stu-id="38c42-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="38c42-105">멤버</span><span class="sxs-lookup"><span data-stu-id="38c42-105">Members</span></span>  
  
|<span data-ttu-id="38c42-106">멤버</span><span class="sxs-lookup"><span data-stu-id="38c42-106">Member</span></span>|<span data-ttu-id="38c42-107">설명</span><span class="sxs-lookup"><span data-stu-id="38c42-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="38c42-108">런타임에 알 수 없는 이유로 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="38c42-109">가비지 수집 요청을 처리 하는 런타임 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="38c42-110">가비지 컬렉션 관련 콜백 간에 발생는 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 및 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="38c42-111">런타임이 일시 중단 하는 `AppDomain` 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="38c42-112">런타임은 일시 중지를 확인 하는 스레드가 `AppDomain` 즉 종료 되 고 다시 시작 될 때 중단 되도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="38c42-113">없는 `AppDomain`-이 일시 중단 하는 동안 특정 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="38c42-114">런타임은 코드 피칭 발생할 수 있도록 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="38c42-115">코드 피칭 계속은 경우에 적시에 (JIT) 컴파일러 활성 코드 피칭 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="38c42-116">코드 피칭 콜백이 발생 간에 `ICorProfilerCallback::RuntimeSuspendFinished` 및 `ICorProfilerCallback::RuntimeResumeStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="38c42-117">**참고:** 하므로이 값은 2.0에서 사용 되지 CLR JIT.NET framework 버전 2.0, 하지 함수 던지기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="38c42-118">런타임에서 종료할 수 있도록 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="38c42-119">작업을 완료 하려면 모든 스레드를 일시 중단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="38c42-120">런타임은 프로세스의 디버깅에 대 한 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="38c42-121">런타임은은 가비지 수집을 위해 준비 하려면 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="38c42-122">런타임은은 JIT 다시 컴파일을 위해 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38c42-123">설명</span><span class="sxs-lookup"><span data-stu-id="38c42-123">Remarks</span></span>  
 <span data-ttu-id="38c42-124">모든 런타임 스레드는 관리 되지 않는 코드에는 런타임에 대해, 이때 것도 일시 중단 됩니다 런타임 재개할 때까지 다시 입력 하려고 시도할 때까지 실행을 계속 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="38c42-125">런타임에 입력 하는 새 스레드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="38c42-126">런타임 내에서 모든 스레드가 중단 가능한 코드에 있는 경우 즉시 일시 중지 되었거나 중단 가능한 코드에 도달할 때 일시 중지 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c42-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38c42-127">Requirements</span></span>  
 <span data-ttu-id="38c42-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38c42-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c42-129">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38c42-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38c42-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38c42-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38c42-131">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c42-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c42-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38c42-132">See Also</span></span>  
 [<span data-ttu-id="38c42-133">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="38c42-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
