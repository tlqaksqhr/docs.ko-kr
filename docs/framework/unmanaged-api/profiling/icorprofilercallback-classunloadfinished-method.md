---
title: ICorProfilerCallback::ClassUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebf72fe4f9fae5b3d791e6eed2e9421b9f4e3296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450819"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="0ced5-102">ICorProfilerCallback::ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="0ced5-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="0ced5-103">클래스 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ced5-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ced5-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ced5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ced5-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0ced5-106">[in] 로드 된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0ced5-107">[in] 클래스 로드 되었는지 여부를 하지 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ced5-108">설명</span><span class="sxs-lookup"><span data-stu-id="0ced5-108">Remarks</span></span>  
 <span data-ttu-id="0ced5-109">클래스 언로드 작업의 일부 후 계속 사용할 수는 `ClassUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="0ced5-110">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="0ced5-111">그러나 성공 HRESULT에 `hrStatus` 클래스 언로드 작업의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ced5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ced5-112">Requirements</span></span>  
 <span data-ttu-id="0ced5-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ced5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ced5-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ced5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ced5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ced5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ced5-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ced5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ced5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ced5-117">See Also</span></span>  
 [<span data-ttu-id="0ced5-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ced5-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="0ced5-119">ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="0ced5-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
