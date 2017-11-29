---
title: "ICorProfilerCallback::ModuleLoadFinished 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22533187da02d34ac2990f351b13bd892a760620
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="3de79-102">ICorProfilerCallback::ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="3de79-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="3de79-103">모듈 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de79-104">구문</span><span class="sxs-lookup"><span data-stu-id="3de79-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3de79-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3de79-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3de79-106">[in] 로드가 완료 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3de79-107">[in] 모듈이 성공적으로 로드 되 고 있는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3de79-108">설명</span><span class="sxs-lookup"><span data-stu-id="3de79-108">Remarks</span></span>  
 <span data-ttu-id="3de79-109">값 `moduleId` 될 때까지 정보 요청에 유효 하지는 `ModuleLoadFinished` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="3de79-110">일부 모듈 로드 후 계속 사용할 수는 `ModuleLoadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="3de79-111">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3de79-112">그러나 성공 HRESULT에서 `hrStatus` 로드 된 모듈의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de79-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3de79-113">Requirements</span></span>  
 <span data-ttu-id="3de79-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3de79-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de79-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3de79-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3de79-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3de79-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3de79-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de79-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de79-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3de79-118">See Also</span></span>  
 [<span data-ttu-id="3de79-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3de79-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3de79-120">ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="3de79-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
