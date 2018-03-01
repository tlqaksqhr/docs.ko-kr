---
title: ICorDebugFunctionBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 019a94243773fcb1751f419d8e38a6759fa1d3bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="d5625-102">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="d5625-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="d5625-103">ICorDebugBreakpoint 인터페이스 함수에서 중단점을 지원 하도록 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5625-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5625-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d5625-104">Methods</span></span>  
  
|<span data-ttu-id="d5625-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d5625-105">Method</span></span>|<span data-ttu-id="d5625-106">설명</span><span class="sxs-lookup"><span data-stu-id="d5625-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5625-107">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="d5625-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="d5625-108">중단점이 설정 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5625-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="d5625-109">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="d5625-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="d5625-110">함수 내에서 중단점의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5625-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5625-111">설명</span><span class="sxs-lookup"><span data-stu-id="d5625-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5625-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5625-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5625-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5625-113">Requirements</span></span>  
 <span data-ttu-id="d5625-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5625-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5625-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5625-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5625-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5625-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5625-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5625-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5625-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5625-118">See Also</span></span>  
 [<span data-ttu-id="d5625-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5625-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
