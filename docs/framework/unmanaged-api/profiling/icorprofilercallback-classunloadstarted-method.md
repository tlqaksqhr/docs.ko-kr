---
title: "ICorProfilerCallback::ClassUnloadStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 994fe840f728b244e5a6e6c83c03340961c30413
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="7bf3a-102">ICorProfilerCallback::ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="7bf3a-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="7bf3a-103">클래스를 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7bf3a-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bf3a-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bf3a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bf3a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7bf3a-106">[in] 언로드되고 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf3a-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bf3a-107">설명</span><span class="sxs-lookup"><span data-stu-id="7bf3a-107">Remarks</span></span>  
 <span data-ttu-id="7bf3a-108">값 `classId` 후 정보 요청에 유효 하지는 `ClassUnloadStarted` 메서드 반환-의이 클래스에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf3a-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf3a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bf3a-109">Requirements</span></span>  
 <span data-ttu-id="7bf3a-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf3a-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7bf3a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7bf3a-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bf3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bf3a-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf3a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bf3a-114">See Also</span></span>  
 [<span data-ttu-id="7bf3a-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bf3a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7bf3a-116">ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="7bf3a-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
