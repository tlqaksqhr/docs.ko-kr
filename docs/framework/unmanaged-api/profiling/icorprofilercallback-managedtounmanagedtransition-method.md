---
title: ICorProfilerCallback::ManagedToUnmanagedTransition 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0735e4c59ba609ed87d61aca737c4f8a4dab757a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453488"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="a3c86-102">ICorProfilerCallback::ManagedToUnmanagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="a3c86-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="a3c86-103">관리 코드에서 비관리 코드로 전환 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c86-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3c86-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3c86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3c86-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a3c86-106">[in] 호출 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="a3c86-107">[in] 값은 [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) 전환 관리 코드에서 비관리 코드로 호출으로 인해 또는 관리 되는 함수에 의해 관리 되지 않는 호출에서 반환 된 오류로 인해 발생 했는지 여부를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3c86-108">설명</span><span class="sxs-lookup"><span data-stu-id="a3c86-108">Remarks</span></span>  
 <span data-ttu-id="a3c86-109">하는 경우의 값 `reason` COR_PRF_TRANSITION_CALL, 함수는 관리 되지 않는 함수는 됩니다 하지 컴파일된-just-in-time 컴파일러를 사용 하 여 ID가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="a3c86-110">관리 되지 않는 함수 그와 관련 된 이름 및 몇 가지 메타 데이터와 같은 기본 정보를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="a3c86-111">암시적 플랫폼을 사용 하 여 관리 되지 않는 함수가 호출 되 면 호출 (PInvoke), 런타임에서 호출의 대상 및 값을 확인할 수 없습니다 `functionId` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="a3c86-112">암시적 PInvoke에 대 한 자세한 내용은 참조 하십시오. [c + + Interop를 사용 하 여 (암시적 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c86-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3c86-113">Requirements</span></span>  
 <span data-ttu-id="a3c86-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c86-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3c86-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3c86-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3c86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c86-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c86-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3c86-118">See Also</span></span>  
 [<span data-ttu-id="a3c86-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3c86-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a3c86-120">UnmanagedToManagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="a3c86-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [<span data-ttu-id="a3c86-121">C++에서 명시적 PInvoke 사용(DllImport 특성)</span><span class="sxs-lookup"><span data-stu-id="a3c86-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
