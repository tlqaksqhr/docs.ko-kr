---
title: "ICorProfilerCallback::JITFunctionPitched 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48432911d7844e6519689961c985da37219179a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="265c1-102">ICorProfilerCallback::JITFunctionPitched 메서드</span><span class="sxs-lookup"><span data-stu-id="265c1-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="265c1-103">프로파일러에 알립니다 하는 시간 (JIT) 된 함수-컴파일된 메모리에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="265c1-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="265c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="265c1-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="265c1-106">[in] 제거 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="265c1-107">설명</span><span class="sxs-lookup"><span data-stu-id="265c1-107">Remarks</span></span>  
 <span data-ttu-id="265c1-108">제거 된 함수가 호출 되는 경우 프로파일러 함수를 다시 컴파일할 때 새 JIT 컴파일 이벤트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="265c1-109">현재, 공용 언어 런타임 (CLR) JIT 컴파일러가 함수를 제거 하지 메모리에서이 콜백은 현재 사용 하지 않는 고 프로파일러에서 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="265c1-110">값 `functionId` 함수를 다시 컴파일할 때까지 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="265c1-111">함수를 다시 컴파일할 때 동일한 `functionId` 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265c1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="265c1-112">Requirements</span></span>  
 <span data-ttu-id="265c1-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="265c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265c1-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="265c1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="265c1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="265c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="265c1-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265c1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="265c1-117">See Also</span></span>  
 [<span data-ttu-id="265c1-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="265c1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
