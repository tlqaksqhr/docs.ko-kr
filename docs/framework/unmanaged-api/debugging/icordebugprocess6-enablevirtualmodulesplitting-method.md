---
title: "ICorDebugProcess6::EnableVirtualModuleSplitting 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34a2c2571ba7f3560d861d0a5271cc3a955253a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="84ba4-102">ICorDebugProcess6::EnableVirtualModuleSplitting 메서드</span><span class="sxs-lookup"><span data-stu-id="84ba4-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>
<span data-ttu-id="84ba4-103">가상 모듈 분할을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ba4-104">구문</span><span class="sxs-lookup"><span data-stu-id="84ba4-104">Syntax</span></span>  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84ba4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84ba4-105">Parameters</span></span>  
 `enableSplitting`  
 <span data-ttu-id="84ba4-106">가상 모듈 분할을 사용하려면 `true`로 설정하고, 사용하지 않으려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84ba4-107">설명</span><span class="sxs-lookup"><span data-stu-id="84ba4-107">Remarks</span></span>  
 <span data-ttu-id="84ba4-108">가상 모듈 분할 원인 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 처리 하 고 대형 모듈 하나가 아닌 개별 모듈의 그룹으로 표시 하는 빌드 중에 병합 된 모듈을 인식 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-108">Virtual module splitting causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="84ba4-109">다양 한 동작을 변경 이렇게 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 아래 설명 된 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-109">Doing this changes the behavior of various [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84ba4-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="84ba4-111">언제든지 이 메서드를 호출하여 `enableSplitting`의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="84ba4-112">모든 상태 저장 기능 변경 내용을 발생 하지 않습니다는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 에 나와 있는 메서드 동작이 변경 이외의 개체는 [가상 모듈 분할 및 관리 되지 않는 디버깅 Api](#APIs) 호출 될 때 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-112">It does not cause any stateful functional changes in an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="84ba4-113">가상 모듈을 사용하는 경우 해당 메서드를 호출할 때 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="84ba4-114">또한 가상화 된 메타 데이터의 중요 한 메모리에 캐시 해야 할 수 있지만 올바르게 구현는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Api와, 이러한 캐시 가상 모듈 분할 해제 되었습니다. 한 후에 유지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="84ba4-115">용어</span><span class="sxs-lookup"><span data-stu-id="84ba4-115">Terminology</span></span>  
 <span data-ttu-id="84ba4-116">아래에는 가상 모듈 분할을 설명하는 데 사용되는 용어가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="84ba4-117">컨테이너 모듈/컨테이너</span><span class="sxs-lookup"><span data-stu-id="84ba4-117">container modules, or containers</span></span>  
 <span data-ttu-id="84ba4-118">집계 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="84ba4-119">하위 모듈/가상 모듈</span><span class="sxs-lookup"><span data-stu-id="84ba4-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="84ba4-120">컨테이너에 있는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="84ba4-121">일반 모듈</span><span class="sxs-lookup"><span data-stu-id="84ba4-121">regular modules</span></span>  
 <span data-ttu-id="84ba4-122">빌드 시에 병합되지 않은 모듈로,</span><span class="sxs-lookup"><span data-stu-id="84ba4-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="84ba4-123">컨테이너 모듈도 아니고 하위 모듈도 아닌 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="84ba4-124">컨테이너 모듈과 하위 모듈 ICorDebugModule 인터페이스 개체로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="84ba4-125">그러나 인터페이스의 동작은 약간씩 다르며 이러한 각각의 경우로는 \<섹션으로 x ref > 섹션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="84ba4-126">모듈 및 어셈블리</span><span class="sxs-lookup"><span data-stu-id="84ba4-126">Modules and assemblies</span></span>  
 <span data-ttu-id="84ba4-127">다중 모듈 어셈블리는 어셈블리 병합 시나리오에서 지원되지 않으므로 모듈과 어셈블리 간에는 일 대 일 관계가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="84ba4-128">컨테이너 모듈 또는 하위 모듈을 나타내는 여부에 관계 없이 각 ICorDebugModule 개체는 해당 ICorDebugAssembly 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="84ba4-129">[icordebugmodule:: Getassembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) 어셈블리에 모듈에서 메서드를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-129">The [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="84ba4-130">반대 방향으로 매핑하려는 [icordebugassembly:: Enumeratemodules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) 메서드는 모듈을 하나만 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="84ba4-131">이 경우 어셈블리와 모듈은 긴밀하게 결합된 쌍을 형성하므로 '어셈블리'와 '모듈'이라는 용어는 거의 동일한 의미로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="84ba4-132">동작 차이점</span><span class="sxs-lookup"><span data-stu-id="84ba4-132">Behavioral differences</span></span>  
 <span data-ttu-id="84ba4-133">컨테이너 모듈의 동작 및 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-133">Container modules have the following behaviors and characteristics:</span></span>  
  
-   <span data-ttu-id="84ba4-134">컨테이너 모듈을 구성하는 모든 하위 모듈의 메타데이터는 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
-   <span data-ttu-id="84ba4-135">형식 이름이 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-135">Their type names may be mangled.</span></span>  
  
-   <span data-ttu-id="84ba4-136">[icordebugmodule:: Getname](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) 메서드는 디스크의 모듈에 경로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-136">The [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
-   <span data-ttu-id="84ba4-137">[icordebugmodule:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) 메서드 해당 이미지의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-137">The [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
-   <span data-ttu-id="84ba4-138">ICorDebugAssembly3.EnumerateContainedAssemblies 메서드는 하위 모듈을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
-   <span data-ttu-id="84ba4-139">ICorDebugAssembly3.GetContainerAssembly 메서드는 `S_FALSE`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="84ba4-140">하위 모듈의 동작 및 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
-   <span data-ttu-id="84ba4-141">병합된 원래 어셈블리에 해당하는 축소된 메타데이터 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
-   <span data-ttu-id="84ba4-142">메타데이터 이름이 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-142">The metadata names are not mangled.</span></span>  
  
-   <span data-ttu-id="84ba4-143">메타데이터 토큰이 빌드 프로세스에서 병합되기 전의 원래 어셈블리에 포함되어 있던 토큰과 일치할 가능성은 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
-   <span data-ttu-id="84ba4-144">[icordebugmodule:: Getname](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) 메서드는 파일 경로가 아닌 어셈블리 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-144">The [ICorDebugModule::GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
-   <span data-ttu-id="84ba4-145">[icordebugmodule:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) 메서드 원래 병합 되지 않은 이미지 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-145">The [ICorDebugModule::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
-   <span data-ttu-id="84ba4-146">ICorDebugModule3.EnumerateContainedAssemblies 메서드는 `S_FALSE`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
-   <span data-ttu-id="84ba4-147">ICorDebugAssembly3.GetContainerAssembly 메서드는 포함하는 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="84ba4-148">모듈에서 검색되는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84ba4-148">Interfaces retrieved from modules</span></span>  
 <span data-ttu-id="84ba4-149">다양한 인터페이스를 만들거나 모듈에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="84ba4-150">여기에는 다음과 같은 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-150">Some of these include:</span></span>  
  
-   <span data-ttu-id="84ba4-151">반환 되는 ICorDebugClass 개체는 [icordebugmodule:: Getclassfromtoken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="84ba4-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
-   <span data-ttu-id="84ba4-152">반환 되는 ICorDebugAssembly 개체는 [icordebugmodule:: Getassembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="84ba4-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="84ba4-153">이러한 개체는 항상 하 여 캐시 되기 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), 및 작성 되거나 컨테이너 모듈 또는 하위 모듈에서 쿼리 된 여부에 관계 없이 같은 포인터 id를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-153">These objects are always cached by [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="84ba4-154">하위 모듈은 이와 같은 캐시된 개체의 필터링된 보기를 제공하며 자체 복사본이 포함된 별도의 캐시를 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="84ba4-155">가상 모듈 분할 및 관리되지 않는 디버깅 API</span><span class="sxs-lookup"><span data-stu-id="84ba4-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  
 <span data-ttu-id="84ba4-156">다음 표에서는 가상 모듈 분할이 관리되지 않는 디버깅 API의 다른 메서드 동작에 주는 영향을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="84ba4-157">메서드</span><span class="sxs-lookup"><span data-stu-id="84ba4-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="84ba4-158">Icordebugfunction:: Getmodule</span><span class="sxs-lookup"><span data-stu-id="84ba4-158">ICorDebugFunction::GetModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="84ba4-159">이 함수가 원래 정의된 하위 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="84ba4-160">이 함수가 병합된 컨테이너 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="84ba4-161">Icordebugclass:: Getmodule</span><span class="sxs-lookup"><span data-stu-id="84ba4-161">ICorDebugClass::GetModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="84ba4-162">이 클래스가 원래 정의된 하위 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="84ba4-163">이 클래스가 병합된 컨테이너 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="84ba4-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="84ba4-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="84ba4-165">로드된 컨테이너 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="84ba4-166">이 설정에 관계없이 하위 모듈에는 로드 이벤트가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="84ba4-167">로드된 컨테이너 모듈을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="84ba4-168">Icordebugappdomain:: Enumerateassemblies</span><span class="sxs-lookup"><span data-stu-id="84ba4-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="84ba4-169">하위 어셈블리와 일반 어셈블리 목록을 반환합니다. 컨테이너 어셈블리는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="84ba4-170">**참고:** 컨테이너 어셈블리에 기호가 없으면 경우 없음 해당 하위 어셈블리가 열거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="84ba4-171">일반 어셈블리의 경우 기호가 없으면 열거될 수도 있고 열거되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="84ba4-172">컨테이너 어셈블리와 일반 어셈블리 목록을 반환합니다. 하위 어셈블리는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="84ba4-173">**참고:** 일반 어셈블리에 기호가 없으면 경우 그렇지 열거 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="84ba4-174">[Icordebugcode:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (IL 코드에만 참조) 하는 경우</span><span class="sxs-lookup"><span data-stu-id="84ba4-174">[ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="84ba4-175">병합 전 어셈블리 이미지에서 유효했던 IL을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="84ba4-176">즉, 참조하는 형식이 IL을 포함하는 가상 모듈에 정의되어 있지 않으면 모든 인라인 메타데이터 토큰은 TypeRef 또는 MemberRef 토큰이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="84ba4-177">이러한 TypeRef 또는 MemberRef 토큰을 조회할 수 있습니다는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 해당 가상 ICorDebugModule 개체에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="84ba4-178">병합 후 어셈블리 이미지의 IL을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84ba4-179">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84ba4-179">Requirements</span></span>  
 <span data-ttu-id="84ba4-180">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84ba4-180">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84ba4-181">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84ba4-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84ba4-182">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84ba4-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84ba4-183">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84ba4-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ba4-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84ba4-184">See Also</span></span>  
 [<span data-ttu-id="84ba4-185">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84ba4-185">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="84ba4-186">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84ba4-186">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
