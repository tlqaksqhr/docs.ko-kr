---
title: "CorGCReferenceType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="6279f-102">CorGCReferenceType 열거형</span><span class="sxs-lookup"><span data-stu-id="6279f-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="6279f-103">가비지가 수집될 개체의 소스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6279f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6279f-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="6279f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6279f-105">Members</span></span>  
  
|<span data-ttu-id="6279f-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="6279f-106">Member name</span></span>|<span data-ttu-id="6279f-107">설명</span><span class="sxs-lookup"><span data-stu-id="6279f-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="6279f-108">개체 참조 테이블의 강력한 참조에 대한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="6279f-109">개체 핸들 테이블의 고정 된 강력한 참조에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="6279f-110">개체 핸들 테이블의 약한 참조에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="6279f-111">개체 핸들 테이블의 약한 참조 횟수가 계산 개체에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="6279f-112">개체 핸들 테이블의 참조 횟수가 계산 개체에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="6279f-113">개체 핸들 테이블의 종속 개체에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="6279f-114">개체 핸들 테이블의 비동기 고정된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="6279f-115">가비지 컬렉션 시 모든 개체 및 개체 루트의 집합 클로저의 대략적인 크기를 유지하는 강력한 핸들입니다. </span><span class="sxs-lookup"><span data-stu-id="6279f-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="6279f-116">관리 되는 스택에서 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="6279f-117">종료자 큐의 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="6279f-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="6279f-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="6279f-119">핸들 테이블의 강력한 참조만를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="6279f-120">이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="6279f-121">핸들 테이블의 약한 참조만를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="6279f-122">이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="6279f-123">핸들 테이블의 모든 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-123">Return all references from the handle table.</span></span> <span data-ttu-id="6279f-124">이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6279f-125">설명</span><span class="sxs-lookup"><span data-stu-id="6279f-125">Remarks</span></span>  
 <span data-ttu-id="6279f-126">`CorGCReferenceType` 열거형 다음과 같이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="6279f-127">값으로는 `type` 필드는 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 구조, 참조 또는 핸들의 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="6279f-128">로 `types` 인수에는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드를 열거에 포함 하는 핸들의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6279f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6279f-129">Requirements</span></span>  
 <span data-ttu-id="6279f-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6279f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6279f-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6279f-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6279f-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6279f-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6279f-133">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6279f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6279f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6279f-134">See Also</span></span>  
 [<span data-ttu-id="6279f-135">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6279f-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
