---
title: "ICorProfilerCallback::FunctionUnloadStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.FunctionUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 957b5a89dbb3e780b0e5512afe405e669fdbecce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="d6076-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="d6076-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="d6076-103">함수를 언로드할 수는 런타임에서 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d6076-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6076-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6076-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6076-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6076-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d6076-106">[in] 언로드되고 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d6076-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6076-107">설명</span><span class="sxs-lookup"><span data-stu-id="d6076-107">Remarks</span></span>  
 <span data-ttu-id="d6076-108">값은 `functionId` 호출자에 게이 메서드에서 반환 된 후 매개 변수는 더 이상 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6076-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6076-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6076-109">Requirements</span></span>  
 <span data-ttu-id="d6076-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6076-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6076-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6076-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6076-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6076-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6076-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6076-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6076-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6076-114">See Also</span></span>  
 [<span data-ttu-id="d6076-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6076-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
