---
title: "ICorProfilerCallback::ModuleAttachedToAssembly 메서드"
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
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6183014bf5487d0eebccf2fb70a13c363212046b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="2dcdc-102">ICorProfilerCallback::ModuleAttachedToAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="2dcdc-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="2dcdc-103">모듈 부모 어셈블리에 연결 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dcdc-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dcdc-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dcdc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dcdc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2dcdc-106">[in] 연결 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="2dcdc-107">[in] 모듈을 연결할 부모 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dcdc-108">설명</span><span class="sxs-lookup"><span data-stu-id="2dcdc-108">Remarks</span></span>  
 <span data-ttu-id="2dcdc-109">호출을 통해 가져오기 주소 테이블 (IAT)을 통해 모듈을 로드할 수 있습니다 `LoadLibrary`, 또는 메타 데이터 참조를 통해.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="2dcdc-110">결과적으로, 공용 언어 런타임 (CLR) 로더 모듈 거주 하는 어셈블리를 확인 하기 위한 여러 코드 경로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="2dcdc-111">따라서, 후 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 호출, 모듈에 어셈블리를 알 수 없습니다에 이며 부모 어셈블리 ID를 가져오는 것은 가능 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="2dcdc-112">`ModuleAttachedToAssembly` 메서드는 모듈 부모 어셈블리 ID를 가져올 수 부모 어셈블리에 연결 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dcdc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dcdc-113">Requirements</span></span>  
 <span data-ttu-id="2dcdc-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcdc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dcdc-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dcdc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dcdc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dcdc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dcdc-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dcdc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcdc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dcdc-118">See Also</span></span>  
 [<span data-ttu-id="2dcdc-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dcdc-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
