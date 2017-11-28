---
title: "COR_PRF_GC_ROOT_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="d7614-102">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="d7614-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="d7614-103">가비지 수집 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7614-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7614-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d7614-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d7614-105">Members</span></span>  
  
|<span data-ttu-id="d7614-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d7614-106">Member</span></span>|<span data-ttu-id="d7614-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7614-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="d7614-108">루트 개체를 이동에서 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="d7614-109">루트는 가비지 수집을 방해 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="d7614-110">루트 개체 자체가 아니라 개체의 필드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="d7614-111">루트 개체의 참조 횟수 특정 값이 있으면 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7614-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7614-112">Remarks</span></span>  
 <span data-ttu-id="d7614-113">`COR_PRF_GC_ROOT_FLAGS`특수 루트에 대 한 추가 정보를 제공 하는 비트 마스크가입니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="d7614-114">그러나 일부 루트는 특별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-114">However, not all roots are special.</span></span> <span data-ttu-id="d7614-115">예를 들어 일부 루트는 약한 참조를 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="d7614-116">이러한 루트 전달할 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="d7614-117">따라서 등이 열거형을 사용 하는 메서드는 [icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 메서드를 모든 플래그를 나타내는 플래그 비트 마스크에 대 한 송신 0은 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7614-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7614-118">Requirements</span></span>  
 <span data-ttu-id="d7614-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7614-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7614-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7614-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7614-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7614-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7614-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7614-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7614-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7614-123">See Also</span></span>  
 [<span data-ttu-id="d7614-124">프로 파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="d7614-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
