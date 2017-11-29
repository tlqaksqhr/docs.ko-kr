---
title: "IMethodMalloc::Alloc 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae0fa84c08cb8e366db36b6727a3058f24789801
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="f3558-102">IMethodMalloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="f3558-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="f3558-103">새 Microsoft MSIL (intermediate language) 함수 본문에 지정된 된 양의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3558-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3558-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3558-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3558-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="f3558-106">[in] 메서드 본문에 할당할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3558-107">설명</span><span class="sxs-lookup"><span data-stu-id="f3558-107">Remarks</span></span>  
 <span data-ttu-id="f3558-108">할당 된 메모리가이 할당자와 연결 된 모듈의 기준 주소 보다 큰 주소에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="f3558-109">즉, 각 할당자는 특정 모듈에 대 한 만들어지고 해당 기준 주소에서 양수 오프셋에서 메모리 할당을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="f3558-110">경우 `Alloc` 모듈의 기준 주소 보다 큰 주소에서 바이트 수가 요청 된 할당에 실패 e_outofmemory가 실제 사용 가능한 메모리 공간의 크기에 관계 없이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="f3558-111">`Alloc` 와 함께에서 사용할지 메서드는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f3558-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3558-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3558-112">Requirements</span></span>  
 <span data-ttu-id="f3558-113">**플랫폼:** WindSee [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3558-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3558-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3558-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3558-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3558-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3558-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3558-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3558-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3558-117">See Also</span></span>  
 [<span data-ttu-id="f3558-118">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3558-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
