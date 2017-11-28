---
title: "ICorProfilerCallback::ExceptionThrown 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3986ca8205297a36bb54825a7af72aeb9821f75b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="ad59d-102">ICorProfilerCallback::ExceptionThrown 메서드</span><span class="sxs-lookup"><span data-stu-id="ad59d-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="ad59d-103">예외가 throw 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad59d-104">이 함수는 예외는 관리 코드에 도달 하는 경우에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad59d-105">구문</span><span class="sxs-lookup"><span data-stu-id="ad59d-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad59d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad59d-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="ad59d-107">[in] 예외를 throw 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad59d-108">설명</span><span class="sxs-lookup"><span data-stu-id="ad59d-108">Remarks</span></span>  
 <span data-ttu-id="ad59d-109">스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ad59d-110">이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ad59d-111">이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad59d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad59d-112">Requirements</span></span>  
 <span data-ttu-id="ad59d-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad59d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad59d-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad59d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad59d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad59d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad59d-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad59d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad59d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad59d-117">See Also</span></span>  
 [<span data-ttu-id="ad59d-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad59d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
