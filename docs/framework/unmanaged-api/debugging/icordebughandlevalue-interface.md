---
title: ICorDebugHandleValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8df7b46bf22fa1a3a8633cbad7ad1a6582b4860
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="2a592-102">ICorDebugHandleValue Interface1</span><span class="sxs-lookup"><span data-stu-id="2a592-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="2a592-103">디버거에서 가비지 수집에 대 한 핸들을 만든 참조 값을 나타내는 ICorDebugReferenceValue의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a592-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2a592-104">Methods</span></span>  
  
|<span data-ttu-id="2a592-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2a592-105">Method</span></span>|<span data-ttu-id="2a592-106">설명</span><span class="sxs-lookup"><span data-stu-id="2a592-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a592-107">Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="2a592-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="2a592-108">이 참조 하는 핸들을 해제 `ICorDebugHandleValue` 명시적으로 인터페이스 포인터를 해제 하지 않고 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="2a592-109">GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="2a592-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="2a592-110">이 참조 하는 핸들의 종류를 설명 하는 CorDebugHandleType 값을 가져옵니다 `ICorDebugHandleValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a592-111">설명</span><span class="sxs-lookup"><span data-stu-id="2a592-111">Remarks</span></span>  
 <span data-ttu-id="2a592-112">`ICorDebugReferenceValue` 개체 디버깅된 되는 코드의 실행이 중단 되 면 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="2a592-113">`ICorDebugHandleValue` 명시적으로 해제 될 때까지 중단과 continuation, 참조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a592-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a592-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a592-115">Requirements</span></span>  
 <span data-ttu-id="2a592-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a592-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a592-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a592-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a592-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a592-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a592-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a592-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a592-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a592-120">See Also</span></span>  
 [<span data-ttu-id="2a592-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a592-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
