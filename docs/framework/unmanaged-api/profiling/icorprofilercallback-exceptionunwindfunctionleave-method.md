---
title: "ICorProfilerCallback::ExceptionUnwindFunctionLeave 메서드"
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
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eba7f6e5123108a7040bd2185eb57fc703c72c30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="36987-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="36987-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="36987-103">예외 처리의 해제 단계에서 함수 해제 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="36987-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36987-104">구문</span><span class="sxs-lookup"><span data-stu-id="36987-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="36987-105">설명</span><span class="sxs-lookup"><span data-stu-id="36987-105">Remarks</span></span>  
 <span data-ttu-id="36987-106">경우는 `ExceptionUnwindFunctionLeave` 메서드가 호출 되 면 기능 인스턴스 및 해당 스택 데이터 스택에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36987-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="36987-107">프로파일러 스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 호출 하는 동안 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36987-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="36987-108">이때 프로파일러가 차단 및 가비지 수집을 시도 하는 경우 런타임에서이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36987-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="36987-109">또한이 호출 하는 동안 프로파일러 호출 해서는 안 관리 코드에 또는 관리 되는 메모리 할당에서.</span><span class="sxs-lookup"><span data-stu-id="36987-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36987-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36987-110">Requirements</span></span>  
 <span data-ttu-id="36987-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36987-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36987-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36987-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36987-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36987-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36987-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36987-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36987-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36987-115">See Also</span></span>  
 [<span data-ttu-id="36987-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36987-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="36987-117">ExceptionUnwindFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="36987-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
