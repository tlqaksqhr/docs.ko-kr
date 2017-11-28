---
title: "ICorProfilerCallback::UnmanagedToManagedTransition 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 45a2ceb53263e317c5c72695d6bc1e93f8f70bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="0ecb4-102">ICorProfilerCallback::UnmanagedToManagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="0ecb4-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="0ecb4-103">비관리 코드에서 관리 코드로 전환 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ecb4-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ecb4-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ecb4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ecb4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0ecb4-106">[in] 호출 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="0ecb4-107">[in] 값은 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 전환 비관리 코드에서 관리 코드로 호출으로 인해 또는 관리 되는 하나에서 호출 되는 관리 되지 않는 함수에서 반환 된 오류로 인해 발생 했는지 여부를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ecb4-108">설명</span><span class="sxs-lookup"><span data-stu-id="0ecb4-108">Remarks</span></span>  
 <span data-ttu-id="0ecb4-109">하는 경우의 값 `reason` COR_PRF_TRANSITION_RETURN은 및 `functionId` null이 아닌 ID는 관리 되지 않는 함수와 이며 됩니다 하지 컴파일된 타임 (JIT) 컴파일러를 사용 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="0ecb4-110">관리 되지 않는 함수 그와 관련 된 이름 및 몇 가지 메타 데이터와 같은 몇 가지 기본 정보를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="0ecb4-111">하는 경우의 값 `reason` COR_PRF_TRANSITION_CALL,이 호출된 된 함수 (즉, 관리 되는 함수)가 아직 JIT 컴파일된 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ecb4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ecb4-112">Requirements</span></span>  
 <span data-ttu-id="0ecb4-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecb4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ecb4-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ecb4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ecb4-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ecb4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ecb4-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ecb4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecb4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ecb4-117">See Also</span></span>  
 [<span data-ttu-id="0ecb4-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ecb4-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="0ecb4-119">ManagedToUnmanagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="0ecb4-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="0ecb4-120">C++에서 명시적 PInvoke 사용(DllImport 특성)</span><span class="sxs-lookup"><span data-stu-id="0ecb4-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="0ecb4-121">C++ Interop 사용(암시적 PInvoke)</span><span class="sxs-lookup"><span data-stu-id="0ecb4-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
