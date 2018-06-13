---
title: ICorProfilerCallback2::GarbageCollectionFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21f7e9fa0e567063c49caa390ace09c43454b092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451684"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="c7918-102">ICorProfilerCallback2::GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c7918-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="c7918-103">가비지 수집이 완료 되 고 해당 되는 모든 가비지 수집 콜백이 실행 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c7918-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7918-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7918-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c7918-105">설명</span><span class="sxs-lookup"><span data-stu-id="c7918-105">Remarks</span></span>  
 <span data-ttu-id="c7918-106">최종 위치에 개체 검사를 프로파일러에 대 한 안전 때는 `GarbageCollectionFinished` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7918-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7918-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7918-107">Requirements</span></span>  
 <span data-ttu-id="c7918-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7918-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7918-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7918-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7918-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7918-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7918-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7918-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7918-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7918-112">See Also</span></span>  
 [<span data-ttu-id="c7918-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7918-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c7918-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7918-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
