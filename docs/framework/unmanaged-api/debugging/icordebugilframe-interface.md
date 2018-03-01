---
title: ICorDebugILFrame Interface1
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
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1db53f50e942e70517fc06dfd90e75d04158ea9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe-interface1"></a><span data-ttu-id="cc0e0-102">ICorDebugILFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="cc0e0-102">ICorDebugILFrame Interface1</span></span>
<span data-ttu-id="cc0e0-103">Microsoft MSIL (intermediate language) 코드의 스택 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="cc0e0-104">이 인터페이스는 ICorDebugFrame 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc0e0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-105">Methods</span></span>  
  
|<span data-ttu-id="cc0e0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-106">Method</span></span>|<span data-ttu-id="cc0e0-107">설명</span><span class="sxs-lookup"><span data-stu-id="cc0e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc0e0-108">CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="cc0e0-109">명령 포인터 지정된 된 오프셋된 위치를 설정할 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="cc0e0-110">EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="cc0e0-111">이 프레임에는 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="cc0e0-112">EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="cc0e0-113">이 프레임에서 지역 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="cc0e0-114">GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="cc0e0-115">MSIL이 스택 프레임에서 지정 된 인수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="cc0e0-116">GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="cc0e0-117">명령 포인터의 값 및 명령 포인터의 값을 가져온 방법에 대해 설명 하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="cc0e0-118">GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="cc0e0-119">MSIL이 스택 프레임에서 지정 된 로컬 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="cc0e0-120">GetStackDepth 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="cc0e0-121">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-121">Not implemented.</span></span>|  
|[<span data-ttu-id="cc0e0-122">GetStackValue 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="cc0e0-123">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-123">Not implemented.</span></span>|  
|[<span data-ttu-id="cc0e0-124">SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="cc0e0-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="cc0e0-125">MSIL 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc0e0-126">설명</span><span class="sxs-lookup"><span data-stu-id="cc0e0-126">Remarks</span></span>  
 <span data-ttu-id="cc0e0-127">`ICorDebugILFrame` 인터페이스는 특수 한 ICorDebugFrame 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="cc0e0-128">사용 되는 프레임 컴파일된 MSIL 코드 프레임 하거나 타임 (JIT).</span><span class="sxs-lookup"><span data-stu-id="cc0e0-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="cc0e0-129">JIT 컴파일 프레임 둘 다 구현는 `ICorDebugILFrame` 인터페이스와 ICorDebugNativeFrame 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc0e0-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc0e0-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc0e0-131">Requirements</span></span>  
 <span data-ttu-id="cc0e0-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0e0-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc0e0-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc0e0-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc0e0-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc0e0-135">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0e0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0e0-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc0e0-136">See Also</span></span>  
 [<span data-ttu-id="cc0e0-137">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc0e0-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
