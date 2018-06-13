---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459673"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="a01b5-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a01b5-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="a01b5-103">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="a01b5-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="a01b5-104">지정 된 NGen 모듈 및 지정된 된 메서드에 인라인에 정의 된 모든 메서드에 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a01b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="a01b5-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a01b5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a01b5-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="a01b5-107">[in] NGen 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="a01b5-108">[in] 정의 하는 모듈의 식별자 `inlineeMethodId`합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="a01b5-109">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a01b5-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="a01b5-110">[in] 인라인 메서드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="a01b5-111">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a01b5-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="a01b5-112">[out] 나타내는 플래그 여부 `ppEnum` 주어진된 메서드에 인라인 처리 하는 모든 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="a01b5-113">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a01b5-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="a01b5-114">[out] 열거자의 주소에 대 한 포인터</span><span class="sxs-lookup"><span data-stu-id="a01b5-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a01b5-115">설명</span><span class="sxs-lookup"><span data-stu-id="a01b5-115">Remarks</span></span>  
 <span data-ttu-id="a01b5-116">`inlineeModuleId` 및 `inlineeMethodId` 함께 인라인 처리 하지 않을 수 있는 메서드에 대 한 전체 식별자를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="a01b5-117">예를 들어 모듈 `A` 메서드를 정의 `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="a01b5-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="a01b5-118">및 모듈 Bdefines `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="a01b5-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="a01b5-119">또한를 가정해 보겠습니다 `Fancy.AddTwice` 인라인 호출을 `SimpleAdd`합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="a01b5-120">프로파일러는이 열거자를 사용 하 여 어떤 인라인 B 모듈에 정의 된 모든 메서드를 찾을 수 수 `Simple.Add`, 하 고 결과 열거는 `AddTwice`합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="a01b5-121">`inlineeModuleId` 모듈의 식별자 `A`, 및 `inlineeeMethodId` 식별자 `Simple.Add(int a, int b)`합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="a01b5-122">경우 `incompleteData` 함수 뒤에 true가 반환 열거자 인라인 처리 하는 모든 메서드는 지정 된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="a01b5-123">이 한 경우에 발생할 수 있습니다 또는 아직 로드 되지 않은 inliners 모듈의 직접 또는 간접 종속성 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="a01b5-124">프로파일러 정확한 데이터를 필요한 경우 것을 다시 시도해 야 나중에 더 많은 모듈을 로드할 때, 특히 각 모듈을 로드할 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="a01b5-125">`EnumNgenModuleMethodsInliningThisMethod` 에서 제한 사항을 해결 하려면 메서드를 사용할 수 ReJIT에 대 한 인라인 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="a01b5-126">ReJIT 프로파일러를 메서드의 구현을 변경 및 다음 새 코드를 신속 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="a01b5-127">마침을 예를 들어 `Simple.Add` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="a01b5-128">그러나 때문에 `Fancy.AddTwice` 가 이미 인라인 `Simple.Add`를 동일 하 게 동작 이전과 같이 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="a01b5-129">를 해당 제한 사항을 해결 하려면 호출자에 게 인라인 있는 모든 모듈의 모든 메서드에 대 한 검색 `Simple.Add` 사용 하 여 `ICorProfilerInfo5::RequestRejit` 이러한 메서드의 각 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="a01b5-130">메서드는 다시 컴파일된, 새 동작을 갖게 됩니다 `Simple.Add` 이전 동작을 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a01b5-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a01b5-131">Requirements</span></span>  
 <span data-ttu-id="a01b5-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a01b5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a01b5-133">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a01b5-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a01b5-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a01b5-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a01b5-135">**.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a01b5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01b5-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a01b5-136">See Also</span></span>  
 [<span data-ttu-id="a01b5-137">ICorProfilerInfo6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a01b5-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
