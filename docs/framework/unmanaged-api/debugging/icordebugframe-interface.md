---
title: ICorDebugFrame Interface1
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
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: caa3ef9cd52cc872d4ebc96376c104a7b90fb4f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframe-interface1"></a><span data-ttu-id="4ff2c-102">ICorDebugFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="4ff2c-102">ICorDebugFrame Interface1</span></span>
<span data-ttu-id="4ff2c-103">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ff2c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-104">Methods</span></span>  
  
|<span data-ttu-id="4ff2c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-105">Method</span></span>|<span data-ttu-id="4ff2c-106">설명</span><span class="sxs-lookup"><span data-stu-id="4ff2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ff2c-107">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="4ff2c-108">이 기준으로 단계별 실행 작업을 수행 하려면 ICorDebugStepper 가져옵니다 `ICorDebugFrame`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="4ff2c-109">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="4ff2c-110">에 대 한 포인터를 가져옵니다는 `ICorDebugFrame` 현재 체인이 프레임을 호출한 또는 체인에서 가장 안쪽 프레임인이 없으면 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4ff2c-111">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="4ff2c-112">에 대 한 포인터를 가져옵니다는 `ICorDebugFrame` 현재 체인에서이 프레임을 호출한 또는 체인의 가장 바깥쪽 프레임이 없으면 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4ff2c-113">GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="4ff2c-114">이 ICorDebugChain에 대 한 포인터를 가져옵니다 `ICorDebugFrame` 의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="4ff2c-115">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="4ff2c-116">이 스택 프레임과 연결 된 ICorDebugCode에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4ff2c-117">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="4ff2c-118">이 스택 프레임과 연결 된 코드를 포함 하는 ICorDebugFunction에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4ff2c-119">GetFunctionToken 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="4ff2c-120">이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4ff2c-121">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="4ff2c-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="4ff2c-122">이 표시 되는 스택 프레임의 절대 주소 범위를 가져옵니다 `ICorDebugFrame`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ff2c-123">설명</span><span class="sxs-lookup"><span data-stu-id="4ff2c-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff2c-124">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff2c-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ff2c-125">Requirements</span></span>  
 <span data-ttu-id="4ff2c-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff2c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff2c-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ff2c-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ff2c-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ff2c-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ff2c-129">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff2c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff2c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ff2c-130">See Also</span></span>  
 [<span data-ttu-id="4ff2c-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ff2c-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
