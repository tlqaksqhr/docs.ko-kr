---
title: "ICorDebugRegisterSet 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet
helpviewer_keywords: ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ccff205758dee2ffc6a6432ab20b3310147eb06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="52768-102">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52768-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="52768-103">현재 코드를 실행 하는 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52768-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52768-104">메서드</span><span class="sxs-lookup"><span data-stu-id="52768-104">Methods</span></span>  
  
|<span data-ttu-id="52768-105">메서드</span><span class="sxs-lookup"><span data-stu-id="52768-105">Method</span></span>|<span data-ttu-id="52768-106">설명</span><span class="sxs-lookup"><span data-stu-id="52768-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52768-107">GetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="52768-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="52768-108">(현재 코드를 실행 하는 컴퓨터)에서 각 레지스터의 값을 가져옵니다는 비트 마스크에 의해 지정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="52768-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="52768-109">GetRegistersAvailable 메서드</span><span class="sxs-lookup"><span data-stu-id="52768-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="52768-110">비트 마스크를 가져옵니다가 있는 레지스터를 나타내는 `ICorDebugRegisterSet` 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52768-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="52768-111">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="52768-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="52768-112">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52768-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="52768-113">SetRegisters 메서드</span><span class="sxs-lookup"><span data-stu-id="52768-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="52768-114">.NET Framework 버전 2.0에 대 한 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52768-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="52768-115">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="52768-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="52768-116">.NET Framework 2.0에 대 한 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52768-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52768-117">설명</span><span class="sxs-lookup"><span data-stu-id="52768-117">Remarks</span></span>  
 <span data-ttu-id="52768-118">`ICorDebugRegisterSet` 인터페이스는 32 비트 레지스터를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="52768-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="52768-119">사용 하 여는 [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) 추가 레지스터를 필요로 하는 i A 64와 같은 플랫폼에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="52768-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52768-120">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52768-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52768-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52768-121">Requirements</span></span>  
 <span data-ttu-id="52768-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52768-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52768-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52768-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52768-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52768-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52768-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52768-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52768-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52768-126">See Also</span></span>  
 [<span data-ttu-id="52768-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52768-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="52768-128">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52768-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
