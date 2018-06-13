---
title: ICorProfilerCallback::ModuleUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a4637ac7466a575c94f8244168576c4a5542689
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452090"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="9c653-102">ICorProfilerCallback::ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="9c653-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="9c653-103">모듈 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c653-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c653-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c653-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c653-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9c653-106">[in] 로드 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9c653-107">[in] 여부는 모듈이 언로드 되었습니다. 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c653-108">설명</span><span class="sxs-lookup"><span data-stu-id="9c653-108">Remarks</span></span>  
 <span data-ttu-id="9c653-109">값 `moduleId` 후 정보 요청에 유효 하지는 [icorprofilercallback:: Moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="9c653-110">클래스 언로드 작업의 일부 후 계속 사용할 수는 `ModuleUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="9c653-111">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9c653-112">그러나 성공 HRESULT에서 `hrStatus` 언로드 모듈의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c653-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c653-113">Requirements</span></span>  
 <span data-ttu-id="9c653-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c653-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c653-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c653-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c653-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c653-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c653-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c653-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c653-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c653-118">See Also</span></span>  
 [<span data-ttu-id="9c653-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c653-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
