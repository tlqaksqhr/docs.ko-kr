---
title: "ICorProfilerFunctionControl::SetILInstrumentedCodeMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 580d60fe0a6348a163fef9e215cddfc1bc4302b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="2ad2d-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="2ad2d-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="2ad2d-103">지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ad2d-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ad2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ad2d-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="2ad2d-106">[in] 맵의 엔트리 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="2ad2d-107">[in] COR_IL_MAP 항목 배열을 호출자가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="2ad2d-108">이러한 항목의 해석에 대 한 같습니다는 [icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ad2d-109">설명</span><span class="sxs-lookup"><span data-stu-id="2ad2d-109">Remarks</span></span>  
 <span data-ttu-id="2ad2d-110">이 메서드를 호출 하 여 매핑을 설정 디버거를 호출 하 여 매핑을 검색할 수 있습니다. [icordebugilcode2:: Getinstrumentedilmap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="2ad2d-111">또한 스택 추적 및 변수 수명에 대한 IL 오프셋을 계산할 때 디버거가 내부적으로 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad2d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ad2d-112">Requirements</span></span>  
 <span data-ttu-id="2ad2d-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad2d-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ad2d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ad2d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ad2d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ad2d-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad2d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ad2d-117">See Also</span></span>  
 [<span data-ttu-id="2ad2d-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ad2d-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
