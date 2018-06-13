---
title: ICorProfilerCallback::ClassLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df70041497f000bfd4f6dcac2713e8d5e4eb33f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450946"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="42589-102">ICorProfilerCallback::ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="42589-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="42589-103">클래스 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="42589-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42589-104">구문</span><span class="sxs-lookup"><span data-stu-id="42589-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42589-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42589-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="42589-106">[in] 로드 되는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="42589-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42589-107">설명</span><span class="sxs-lookup"><span data-stu-id="42589-107">Remarks</span></span>  
 <span data-ttu-id="42589-108">값 `classId` 될 때까지 정보 요청에 유효 하지는 [icorprofilercallback:: Classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="42589-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42589-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42589-109">Requirements</span></span>  
 <span data-ttu-id="42589-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42589-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42589-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42589-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42589-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42589-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42589-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42589-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42589-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42589-114">See Also</span></span>  
 [<span data-ttu-id="42589-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42589-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
