---
title: ICorDebugReferenceValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d11cb4cbd6baa1e0d381c9fb11d5a3343287cf55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="c13ff-102">ICorDebugReferenceValue Interface1</span><span class="sxs-lookup"><span data-stu-id="c13ff-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="c13ff-103">개체에 대 한 참조 하는 값을 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="c13ff-104">(즉,이 메서드는 포인터를 관리 하는 합니다.) 이 인터페이스는 "ICorDebugValue"를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c13ff-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-105">Methods</span></span>  
  
|<span data-ttu-id="c13ff-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-106">Method</span></span>|<span data-ttu-id="c13ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="c13ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c13ff-108">Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="c13ff-109">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="c13ff-110">DereferenceStrong 메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="c13ff-111">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-111">Not implemented.</span></span> <span data-ttu-id="c13ff-112">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="c13ff-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="c13ff-113">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="c13ff-114">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="c13ff-115">IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="c13ff-116">나타내는 값을 가져옵니다 여부이 `ICorDebugReferenceValue` 는 null 값,이 경우는 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="c13ff-117">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="c13ff-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="c13ff-118">현재 메모리 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-118">Sets the current memory address.</span></span> <span data-ttu-id="c13ff-119">이 메서드가이 설정, 즉 `ICorDebugReferenceValue` 개체를 가리키도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c13ff-120">설명</span><span class="sxs-lookup"><span data-stu-id="c13ff-120">Remarks</span></span>  
 <span data-ttu-id="c13ff-121">공용 언어 런타임 (CLR) 디버깅된 프로세스가 계속 될 때 개체의 가비지 수집을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="c13ff-122">가비지 수집이 메모리에 개체를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="c13ff-123">`ICorDebugReferenceValue` 됩니다 하나 협력 하 여 가비지 수집의 정보는 가비지 수집 후 업데이트 하거나 가비지 수집 전에 암시적으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="c13ff-124">`ICorDebugReferenceValue` 디버깅된 된 프로세스를 계속 한 후 개체 암시적으로 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="c13ff-125">명시적으로 발표 되거나 노출 될 때까지 파생된 "ICorDebugHandleValue" 무효화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c13ff-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13ff-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c13ff-127">Requirements</span></span>  
 <span data-ttu-id="c13ff-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c13ff-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13ff-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c13ff-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c13ff-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c13ff-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c13ff-131">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13ff-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13ff-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c13ff-132">See Also</span></span>  
    
    
 [<span data-ttu-id="c13ff-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c13ff-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
