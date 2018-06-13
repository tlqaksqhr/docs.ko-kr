---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454752"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="5a186-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5a186-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="5a186-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="5a186-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="5a186-104">동적 메서드의 JIT 컴파일 시작 될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a186-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a186-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a186-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a186-106">Parameters</span></span>  
<span data-ttu-id="5a186-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="5a186-107">[in] `functionId`</span></span>  
<span data-ttu-id="5a186-108">컴파일을 시작 되는 JIT에 대 한 메모리 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="5a186-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="5a186-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="5a186-110">`true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시을 나타내기 위해 `false` 차단는 영향을 주지 않는지 런타임에 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="5a186-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="5a186-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="5a186-112">메서드의 IL 헤더의 첫 번째 바이트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="5a186-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="5a186-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="5a186-114">IL 헤더의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="5a186-115">설명</span><span class="sxs-lookup"><span data-stu-id="5a186-115">Remarks</span></span>  

<span data-ttu-id="5a186-116">이 콜백은 동적 메서드가 JIT 컴파일된 있을 때마다 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="5a186-117">다양 한 IL 스텁 및 LCG 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="5a186-118">목표는 사용자에 게 컴파일된 메서드를 식별 하는 충분 한 정보가 프로파일러 작성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="5a186-119">`functionId` 동적 메서드는 메타 데이터가 때문에 해당 메타 데이터 토큰에 해결 하려면 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="5a186-120">`pILHeader` 포인터는 콜백 중에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a186-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a186-121">Requirements</span></span>  
 <span data-ttu-id="5a186-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a186-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a186-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a186-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a186-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a186-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a186-125">**.NET framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a186-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a186-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a186-126">See Also</span></span>  
 [<span data-ttu-id="5a186-127">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="5a186-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [<span data-ttu-id="5a186-128">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a186-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
