---
title: "ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location: mscorwks.dll
api_type: COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f67ef9832a7fb1ff1ec153a4f8aff74079e3b76c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="f8474-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드</span><span class="sxs-lookup"><span data-stu-id="f8474-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="f8474-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="f8474-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f8474-104">프로파일러가에 추가 하는 어셈블리 참조의 공용 언어 런타임 (CLR) 알립니다는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8474-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8474-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8474-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8474-106">Parameters</span></span>  
 <span data-ttu-id="f8474-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="f8474-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="f8474-108">에 대 한 포인터는 [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) CLR 어셈블리 참조 closure 워커를 수행할 때 고려해 야 하는 어셈블리 참조에 대 한 정보를 제공 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8474-109">설명</span><span class="sxs-lookup"><span data-stu-id="f8474-109">Remarks</span></span>  
 <span data-ttu-id="f8474-110">에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대해이 메서드를 호출 하는 프로파일러는 `wszAssemblyPath` 의 인수는 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="f8474-111">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 인터페이스를 전달 하는 프로파일러 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 함께 어셈블리 경로 및 이름에는 `wszAssemblyPath` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8474-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8474-112">Requirements</span></span>  
 <span data-ttu-id="f8474-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8474-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8474-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8474-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8474-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8474-116">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8474-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8474-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8474-117">See Also</span></span>  
 [<span data-ttu-id="f8474-118">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8474-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 [<span data-ttu-id="f8474-119">GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="f8474-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [<span data-ttu-id="f8474-120">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="f8474-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
