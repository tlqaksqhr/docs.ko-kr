---
title: ICorDebugNativeFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 63d631dec00e63d6ee383cd36d79382a529d9ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="913dc-102">ICorDebugNativeFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="913dc-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="913dc-103">네이티브 프레임에 사용 되는 ICorDebugFrame의 특수화 된 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="913dc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-104">Methods</span></span>  
  
|<span data-ttu-id="913dc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-105">Method</span></span>|<span data-ttu-id="913dc-106">설명</span><span class="sxs-lookup"><span data-stu-id="913dc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="913dc-107">CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="913dc-108">네이티브 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정할 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="913dc-109">GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="913dc-110">네이티브 코드로 스택 프레임의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="913dc-111">GetLocalDoubleRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="913dc-112">네이티브 프레임의 두 가지 메모리 레지스터에 저장 된 지역 변수 또는 인수의 값을 나타내는 ICorDebugValue에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="913dc-113">GetLocalMemoryRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="913dc-114">에 대 한 포인터를 가져옵니다는 `ICorDebugValue` 지정된 레지스터에 저장 된 하위 비트가 상위 비트는 지정 된 메모리 주소에 저장 된 지역 변수의 값을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="913dc-115">GetLocalMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="913dc-116">에 대 한 포인터를 가져옵니다는 `ICorDebugValue` 지정 된 메모리 주소에 저장 된 지역 변수의 값을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="913dc-117">GetLocalRegisterMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="913dc-118">에 대 한 포인터를 가져옵니다는 `ICorDebugValue` 상위 비트가 지정한 레지스터에 저장 된 지정 된 메모리 주소에 낮은 비트 저장 된 지역 변수의 값을 나타내는</span><span class="sxs-lookup"><span data-stu-id="913dc-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="913dc-119">GetLocalRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="913dc-120">에 대 한 포인터를 가져옵니다는 `ICorDebugValue` 지정된 된 네이티브 레지스터에 저장 된 지역 변수 또는 인수의 값을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="913dc-121">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="913dc-122">에 대 한 포인터를 가져옵니다는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 레지스터가에 대 한 집합을 나타내는 `ICorDebugNativeFrame`합니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="913dc-123">SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="913dc-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="913dc-124">네이티브 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="913dc-125">설명</span><span class="sxs-lookup"><span data-stu-id="913dc-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="913dc-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="913dc-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="913dc-127">Requirements</span></span>  
 <span data-ttu-id="913dc-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="913dc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="913dc-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="913dc-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="913dc-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="913dc-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="913dc-131">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="913dc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913dc-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="913dc-132">See Also</span></span>  
 [<span data-ttu-id="913dc-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="913dc-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
