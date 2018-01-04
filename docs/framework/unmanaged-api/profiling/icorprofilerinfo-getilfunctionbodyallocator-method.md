---
title: "ICorProfilerInfo::GetILFunctionBodyAllocator 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBodyAllocator
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1feec20f0ddc4f6029490e06d4729b3fdaa7fa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="83282-102">ICorProfilerInfo::GetILFunctionBodyAllocator 메서드</span><span class="sxs-lookup"><span data-stu-id="83282-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="83282-103">Microsoft MSIL (intermediate language) 코드에서 메서드 본문을 바꾸는 데 사용 하는 메모리를 할당 하기 위한 메서드를 제공 하는 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83282-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83282-104">구문</span><span class="sxs-lookup"><span data-stu-id="83282-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83282-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83282-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="83282-106">[in] 메서드가 프로시저가 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="83282-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="83282-107">[out] 에 대 한 포인터는 [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) 메모리를 할당 하는 메서드를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="83282-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83282-108">설명</span><span class="sxs-lookup"><span data-stu-id="83282-108">Remarks</span></span>  
 <span data-ttu-id="83282-109">MSIL 코드에서 메서드 본문은 4GB 내 모듈 따르는지 즉 로드 된 모듈을 기준으로 상대 가상 주소 (RVA)으로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83282-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="83282-110">메서드의 본문 교체 하는 도구에 대 한 잘 띄게 하려면는 `GetILFunctionBodyAllocator` 메서드를 사용 하면 메모리는 해당 범위 내에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83282-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83282-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83282-111">Requirements</span></span>  
 <span data-ttu-id="83282-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83282-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83282-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83282-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83282-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83282-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83282-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83282-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83282-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83282-116">See Also</span></span>  
 [<span data-ttu-id="83282-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83282-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
