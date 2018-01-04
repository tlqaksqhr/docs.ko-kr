---
title: "ICorProfilerCallback::ExceptionCatcherEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCatcherEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a72b2e75ee622bab357046ff29fac4aa9223d7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="f0a7e-102">ICorProfilerCallback::ExceptionCatcherEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="f0a7e-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="f0a7e-103">컨트롤을 적절 한 전달 되는 프로파일러에 알립니다 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0a7e-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0a7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0a7e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f0a7e-106">[in] 포함 하는 함수 식별자는 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="f0a7e-107">[in] 처리 되 고 예외의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a7e-108">설명</span><span class="sxs-lookup"><span data-stu-id="f0a7e-108">Remarks</span></span>  
 <span data-ttu-id="f0a7e-109">`ExceptionCatcherEnter` 타임 (JIT) 컴파일러를 사용 하 여 컴파일된 코드에서 catch 포인터가 있는 경우에 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="f0a7e-110">런타임에서의 내부 코드에 또는 비관리 코드에서 발견 된 예외는이 알림을 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="f0a7e-111">`objectId` 가비지 수집 이후 개체 이동 되었으면 있으므로 값이 다시 전달 된 `ExceptionThrown` 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="f0a7e-112">스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f0a7e-113">이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f0a7e-114">이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a7e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0a7e-115">Requirements</span></span>  
 <span data-ttu-id="f0a7e-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a7e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a7e-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0a7e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0a7e-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0a7e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0a7e-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a7e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a7e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0a7e-120">See Also</span></span>  
 [<span data-ttu-id="f0a7e-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0a7e-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f0a7e-122">ExceptionCatcherLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="f0a7e-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
