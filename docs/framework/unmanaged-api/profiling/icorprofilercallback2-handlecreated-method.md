---
title: "ICorProfilerCallback2::HandleCreated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.HandleCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d866261f16e344f6842ba59e83424219ec3d8dfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="a71c2-102">ICorProfilerCallback2::HandleCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="a71c2-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="a71c2-103">가비지 컬렉션 핸들을 이미 만들었다고 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a71c2-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a71c2-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a71c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a71c2-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="a71c2-106">[in] 가비지 수집에 대 한 핸들의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a71c2-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="a71c2-107">[in] 가비지 수집 핸들의 생성 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a71c2-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a71c2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a71c2-108">Requirements</span></span>  
 <span data-ttu-id="a71c2-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a71c2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a71c2-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a71c2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a71c2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a71c2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a71c2-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a71c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71c2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a71c2-113">See Also</span></span>  
 [<span data-ttu-id="a71c2-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a71c2-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a71c2-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a71c2-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
