---
title: ICorProfilerCallback::AssemblyUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d757a0455992bc82ead922a5fbf4c71f11a9085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450871"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="ad22f-102">ICorProfilerCallback::AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="ad22f-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="ad22f-103">어셈블리 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad22f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad22f-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad22f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad22f-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="ad22f-106">[in] 언로드되고 하는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ad22f-107">[in] 어셈블리가 로드 되었는지 여부를 하지 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad22f-108">설명</span><span class="sxs-lookup"><span data-stu-id="ad22f-108">Remarks</span></span>  
 <span data-ttu-id="ad22f-109">값 `assemblyId` 후 정보 요청에 유효 하지는 [icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="ad22f-110">일부 부분은 어셈블리 언로드 후 계속 사용할 수는 `AssemblyUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="ad22f-111">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ad22f-112">그러나 성공 HRESULT에서 `hrStatus` 어셈블리 언로드 작업의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad22f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad22f-113">Requirements</span></span>  
 <span data-ttu-id="ad22f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad22f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad22f-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad22f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad22f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad22f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad22f-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad22f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad22f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad22f-118">See Also</span></span>  
 [<span data-ttu-id="ad22f-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad22f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
