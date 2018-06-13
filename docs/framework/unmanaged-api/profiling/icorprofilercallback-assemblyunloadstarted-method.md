---
title: ICorProfilerCallback::AssemblyUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10475831be02bd4a958da84b7b75409cf3ad4097
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450527"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="84662-102">ICorProfilerCallback::AssemblyUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="84662-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="84662-103">어셈블리를 언로드하여 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="84662-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84662-104">구문</span><span class="sxs-lookup"><span data-stu-id="84662-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84662-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84662-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="84662-106">[in] 언로드되고 하는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="84662-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84662-107">설명</span><span class="sxs-lookup"><span data-stu-id="84662-107">Remarks</span></span>  
 <span data-ttu-id="84662-108">값 `assemblyId` 후 정보 요청에 유효 하지는 `AssemblyUnloadStarted` 메서드 반환-프로파일러의이 어셈블리에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="84662-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84662-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84662-109">Requirements</span></span>  
 <span data-ttu-id="84662-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84662-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84662-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84662-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84662-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84662-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84662-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84662-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84662-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84662-114">See Also</span></span>  
 [<span data-ttu-id="84662-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84662-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="84662-116">AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="84662-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
