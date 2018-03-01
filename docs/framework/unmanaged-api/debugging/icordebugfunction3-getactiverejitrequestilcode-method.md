---
title: "ICorDebugFunction3::GetActiveReJitRequestILCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae041a9a5973194398bbfed41771396b305f52fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="43ec7-102">ICorDebugFunction3::GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="43ec7-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="43ec7-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="43ec7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="43ec7-104">한 인터페이스 포인터를 가져옵니다는 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 활성 ReJIT 요청의 IL을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ec7-105">구문</span><span class="sxs-lookup"><span data-stu-id="43ec7-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43ec7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43ec7-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="43ec7-107">활성 ReJIT 요청의 IL에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43ec7-108">설명</span><span class="sxs-lookup"><span data-stu-id="43ec7-108">Remarks</span></span>  
 <span data-ttu-id="43ec7-109">이 `ICorDebugFunction3` 개체가 나타내는 메서드에 활성 ReJIT 요청이 있으면 `ppReJitedILCode`는 해당 IL에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="43ec7-110">일반적인 경우가를 활성 요청이 없을 경우 `ppReJitedILCode` 은 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="43ec7-111">실행이 반환 ReJIT 요청이 활성화 되 고 [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="43ec7-112">이 요청에서는 JIT가 아직 컴파일되지 않았을 수 있으며 원래 코드 버전에서 스레드가 계속 실행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="43ec7-113">호출을 하는 동안에 ReJIT 요청이 비활성화 됩니다는 [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="43ec7-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="43ec7-114">IL이 되돌려진 후에도 스레드는 JIT가 다시 컴파일된(ReJIT) 코드를 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43ec7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43ec7-115">Requirements</span></span>  
 <span data-ttu-id="43ec7-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43ec7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ec7-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43ec7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43ec7-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43ec7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43ec7-119">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43ec7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ec7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43ec7-120">See Also</span></span>  
 [<span data-ttu-id="43ec7-121">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43ec7-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="43ec7-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43ec7-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="43ec7-123">방법 가이드는 ReJIT:</span><span class="sxs-lookup"><span data-stu-id="43ec7-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
