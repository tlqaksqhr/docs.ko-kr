---
title: "ICorProfilerCallback6::GetAssemblyReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc2e80d6d8207a869d43beb46cc9448bdd86dfec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="daea0-102">ICorProfilerCallback6::GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="daea0-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="daea0-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="daea0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="daea0-104">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daea0-105">구문</span><span class="sxs-lookup"><span data-stu-id="daea0-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daea0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daea0-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="daea0-107">[in] 메타데이터를 수정할 어셈블리의 경로와 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="daea0-108">[in] 주소에 대 한 포인터는 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 추가를 참조 하는 어셈블리를 지정 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daea0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="daea0-109">Return Value</span></span>  
 <span data-ttu-id="daea0-110">이 콜백의 반환 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daea0-111">설명</span><span class="sxs-lookup"><span data-stu-id="daea0-111">Remarks</span></span>  
 <span data-ttu-id="daea0-112">이 콜백을 설정 하 여 제어는 [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 호출할 때는 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="daea0-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="daea0-113">프로파일러에 대 한 등록 하는 경우는 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드는 런타임에서 전달에 대 한 포인터와 함께 로드할된 어셈블리의 이름과 경로 [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 해당 메서드로 인터페이스 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="daea0-114">프로파일러를 호출할 수는 [icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드는 `COR_PRF_ASSEMBLY_REFERENCE_INFO` 에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체는 `GetAssemblyReferences` 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="daea0-115">프로파일러가 어셈블리 참조를 추가하기 위해 어셈블리 메타데이터를 수정해야 하는 경우에만 `GetAssemblyReferences` 콜백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="daea0-116">(하지만 실제 어셈블리의 메타 데이터 수정에서 수행 하는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)콜백 메서드입니다.) 프로파일러는 `GetAssemblyReferences` 콜백 메서드를 구현하여 모듈 로드 시 어셈블리 참조가 추가될 것임을 CLR(공용 언어 런타임)에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="daea0-117">그러면 프로파일러가 메타데이터 어셈블리 참조를 나중에 수정하더라도 이 초기 단계에서 CLR이 결정하는 어셈블리 공유 여부가 유효하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="daea0-118">따라서 프로파일러 메타데이터 수정으로 인해 발생하는 `SECURITY_E_INCOMPATIBLE_SHARE` 오류 중 일부를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="daea0-119">프로파일러를 사용 하는 [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) CLR 어셈블리 참조 closure 워커에 어셈블리 참조를 추가 하려면이 메서드에서 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="daea0-120">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 개체는이 콜백 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="daea0-121">에 대 한 호출이 [icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메타 데이터가 수정 되었지만 수정 된 어셈블리 참조 closure 워커에만이 콜백에서 메서드 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="daea0-122">프로파일러를 사용 해야 합니다는 [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 내에서 어셈블리 참조를 명시적으로 추가할 개체는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 참조에 대 한 콜백 어셈블리를 구현 하는 경우에는 `GetAssemblyReferences` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="daea0-123">동일한 어셈블리에 대 한이 콜백의 중복 호출을 받을 준비가 되어 있어야 하 고 이러한 중복 호출에 대 한 동일 하 게 응답 하는 프로파일러 (동일한 집합을 만들어서 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 호출).</span><span class="sxs-lookup"><span data-stu-id="daea0-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daea0-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daea0-124">Requirements</span></span>  
 <span data-ttu-id="daea0-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daea0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daea0-126">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="daea0-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="daea0-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daea0-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daea0-128">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daea0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daea0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daea0-129">See Also</span></span>  
 [<span data-ttu-id="daea0-130">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daea0-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [<span data-ttu-id="daea0-131">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="daea0-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="daea0-132">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="daea0-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [<span data-ttu-id="daea0-133">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daea0-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
