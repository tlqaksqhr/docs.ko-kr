---
title: "ICorProfilerCallback::ObjectAllocated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37f4701271f299698d7cd323b7d701f4cb7adb25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="c02ff-102">ICorProfilerCallback::ObjectAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="c02ff-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="c02ff-103">개체에 대 한 할당 된 힙에 메모리 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="c02ff-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c02ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c02ff-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="c02ff-106">[in] 메모리가 할당 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="c02ff-107">[in] 개체 인스턴스 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c02ff-108">설명</span><span class="sxs-lookup"><span data-stu-id="c02ff-108">Remarks</span></span>  
 <span data-ttu-id="c02ff-109">`ObjectedAllocated` 스택 또는 관리 되지 않는 메모리에서 할당에 대 한 메서드가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="c02ff-110">`classId` 매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="c02ff-111">프로파일러는 해당 클래스에 대 한 클래스 부하 콜백을 받습니다 바로 뒤의 `ObjectAllocated` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02ff-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c02ff-112">Requirements</span></span>  
 <span data-ttu-id="c02ff-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c02ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02ff-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c02ff-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c02ff-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c02ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c02ff-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02ff-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c02ff-117">See Also</span></span>  
 [<span data-ttu-id="c02ff-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c02ff-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c02ff-119">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c02ff-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [<span data-ttu-id="c02ff-120">ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c02ff-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
