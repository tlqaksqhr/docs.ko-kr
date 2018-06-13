---
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6169d00065fad57b7ce346ab9029f242eff5498a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451443"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="54f18-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="54f18-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="54f18-103">예외 처리의 해제 단계는에서 함수 해제를 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f18-104">구문</span><span class="sxs-lookup"><span data-stu-id="54f18-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54f18-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54f18-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="54f18-106">[in] 해제 되 고 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f18-107">설명</span><span class="sxs-lookup"><span data-stu-id="54f18-107">Remarks</span></span>  
 <span data-ttu-id="54f18-108">스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="54f18-109">이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="54f18-110">이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f18-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54f18-111">Requirements</span></span>  
 <span data-ttu-id="54f18-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54f18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f18-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="54f18-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="54f18-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54f18-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54f18-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f18-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f18-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54f18-116">See Also</span></span>  
 [<span data-ttu-id="54f18-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54f18-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="54f18-118">ExceptionUnwindFunctionLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="54f18-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
