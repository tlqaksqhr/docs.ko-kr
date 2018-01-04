---
title: "ICorProfilerInfo4::GetReJITIDs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetReJITIDs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="20b7f-102">ICorProfilerInfo4::GetReJITIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="20b7f-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="20b7f-103">모든 JIT 다시 컴파일된 버전의 지정된 된 함수 여전히 할당 되는 식별 하는 Id의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="20b7f-104">여기에 이후에 되돌릴 되었지만 아직 사용할 수 없는 (예를 들어 되돌려 진된 함수를 포함 하는 응용 프로그램 도메인 사용 중인 경우 여전히) 함수의 JIT 다시 컴파일된 버전 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b7f-105">구문</span><span class="sxs-lookup"><span data-stu-id="20b7f-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20b7f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20b7f-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="20b7f-107">[in] `FunctionID` 를 열거할 버전에 대 한 함수 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="20b7f-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="20b7f-108">[in] JIT 다시 컴파일된 Id에 할당 된 수의 `reJitIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="20b7f-109">[out] JIT 다시 컴파일된 Id의 실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="20b7f-110">[out] 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자에 게 할당 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20b7f-111">설명</span><span class="sxs-lookup"><span data-stu-id="20b7f-111">Remarks</span></span>  
 <span data-ttu-id="20b7f-112">`GetReJITIDs`지정 된 함수 인스턴스에 대 한 활성 JIT 다시 컴파일된 Id를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="20b7f-113">다른 동일한 사용 패턴을 따르는 `ICorProfilerInfo` 호출자 할당 버퍼를 허용 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b7f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20b7f-114">Requirements</span></span>  
 <span data-ttu-id="20b7f-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20b7f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b7f-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20b7f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20b7f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20b7f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20b7f-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20b7f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b7f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b7f-119">See Also</span></span>  
 [<span data-ttu-id="20b7f-120">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20b7f-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="20b7f-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20b7f-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="20b7f-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="20b7f-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
