---
title: ICorDebugEnum Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum
helpviewer_keywords: ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f6596918819294f0ab68735cec12f9eab8bf83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="06b29-102">ICorDebugEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="06b29-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="06b29-103">디버깅 응용 프로그램에서 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06b29-104">메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-104">Methods</span></span>  
  
|<span data-ttu-id="06b29-105">메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-105">Method</span></span>|<span data-ttu-id="06b29-106">설명</span><span class="sxs-lookup"><span data-stu-id="06b29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06b29-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="06b29-108">이 파일의 복사본을 만듭니다 `ICorDebugEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="06b29-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="06b29-110">열거형에서 항목의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="06b29-111">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="06b29-112">열거형의 시작 부분으로 커서를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="06b29-113">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="06b29-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="06b29-114">열거형에 커서를 앞으로 항목의 지정한 수 만큼 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b29-115">설명</span><span class="sxs-lookup"><span data-stu-id="06b29-115">Remarks</span></span>  
 <span data-ttu-id="06b29-116">파생 된 다음 열거자 `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="06b29-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="06b29-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="06b29-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="06b29-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="06b29-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="06b29-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="06b29-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="06b29-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="06b29-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="06b29-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="06b29-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="06b29-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="06b29-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="06b29-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="06b29-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="06b29-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="06b29-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="06b29-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="06b29-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="06b29-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="06b29-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="06b29-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="06b29-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="06b29-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="06b29-138">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b29-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06b29-139">Requirements</span></span>  
 <span data-ttu-id="06b29-140">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06b29-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b29-141">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06b29-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06b29-142">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06b29-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06b29-143">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b29-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b29-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06b29-144">See Also</span></span>  
 [<span data-ttu-id="06b29-145">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06b29-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
