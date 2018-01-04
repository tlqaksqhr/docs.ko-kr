---
title: "ICorProfilerCallback::ModuleUnloadStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 384d655254cc79283f93ff2e608b0429c4a84ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="4d3a7-102">ICorProfilerCallback::ModuleUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="4d3a7-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="4d3a7-103">모듈은 언로드됩니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4d3a7-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d3a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d3a7-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d3a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d3a7-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4d3a7-106">[in] 언로드되고 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d3a7-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d3a7-107">설명</span><span class="sxs-lookup"><span data-stu-id="4d3a7-107">Remarks</span></span>  
 <span data-ttu-id="4d3a7-108">값 `moduleId` 후 정보 요청에 유효 하지는 `ModuleUnloadStarted` 메서드 반환-프로파일러의이 모듈에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="4d3a7-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d3a7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d3a7-109">Requirements</span></span>  
 <span data-ttu-id="4d3a7-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d3a7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d3a7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d3a7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d3a7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d3a7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d3a7-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d3a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3a7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d3a7-114">See Also</span></span>  
 [<span data-ttu-id="4d3a7-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d3a7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4d3a7-116">ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="4d3a7-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
