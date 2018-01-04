---
title: "ICorProfilerCallback::AssemblyUnloadStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9984cff1d3c4013d66bc9eb7dbe5dbe7b61d2ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="04650-102">ICorProfilerCallback::AssemblyUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="04650-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="04650-103">어셈블리를 언로드하여 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="04650-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04650-104">구문</span><span class="sxs-lookup"><span data-stu-id="04650-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04650-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04650-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="04650-106">[in] 언로드되고 하는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="04650-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04650-107">설명</span><span class="sxs-lookup"><span data-stu-id="04650-107">Remarks</span></span>  
 <span data-ttu-id="04650-108">값 `assemblyId` 후 정보 요청에 유효 하지는 `AssemblyUnloadStarted` 메서드 반환-프로파일러의이 어셈블리에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="04650-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04650-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04650-109">Requirements</span></span>  
 <span data-ttu-id="04650-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04650-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04650-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04650-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04650-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04650-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04650-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04650-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04650-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04650-114">See Also</span></span>  
 [<span data-ttu-id="04650-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04650-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="04650-116">AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="04650-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
