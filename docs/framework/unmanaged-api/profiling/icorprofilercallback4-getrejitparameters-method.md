---
title: "ICorProfilerCallback4::GetReJITParameters 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03e5440fbd016f52642a5626b0cf0b82e7ecea45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="b30a2-102">ICorProfilerCallback4::GetReJITParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="b30a2-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="b30a2-103">새 다시 컴파일된 메서드 본문에 대 한 대체 코드 생성 플래그를 설정 하려면 코드 프로파일러를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b30a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b30a2-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b30a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b30a2-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b30a2-106">[in] CLR JIT 다시 컴파일을 매개 변수를 필요한 메서드를 포함 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="b30a2-107">[in] `MethodDef` 메서드의 CLR JIT 다시 컴파일을 매개 변수를 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="b30a2-108">[in] 에 대 한 포인터는 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 프로파일러 컴파일할 메서드에 대 한 JIT 다시 컴파일을 정보를 제공 하는 데 사용할 수 있는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b30a2-109">설명</span><span class="sxs-lookup"><span data-stu-id="b30a2-109">Remarks</span></span>  
 <span data-ttu-id="b30a2-110">CLR 문제는 `GetReJITParameters` 콜백 프로파일러는 지정 된 메서드를 다시 컴파일할 수에 대 한 매개 변수를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="b30a2-111">`GetReJITParameters` 콜백 함수 당 한 번만 실행 될 있으며 프로파일러에서 제공 된 매개 변수는 해당 함수의 모든 인스턴스에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b30a2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b30a2-112">Requirements</span></span>  
 <span data-ttu-id="b30a2-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b30a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b30a2-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b30a2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b30a2-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b30a2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b30a2-116">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b30a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30a2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b30a2-117">See Also</span></span>  
 [<span data-ttu-id="b30a2-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b30a2-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b30a2-119">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b30a2-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="b30a2-120">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="b30a2-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="b30a2-121">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="b30a2-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
