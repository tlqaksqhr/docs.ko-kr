---
title: ICorDebugCode Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86659b624ef01922b6c5d1db9b3ae3697d0128b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode-interface1"></a><span data-ttu-id="4caa2-102">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="4caa2-102">ICorDebugCode Interface1</span></span>
<span data-ttu-id="4caa2-103">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4caa2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-104">Methods</span></span>  
  
|<span data-ttu-id="4caa2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-105">Method</span></span>|<span data-ttu-id="4caa2-106">설명</span><span class="sxs-lookup"><span data-stu-id="4caa2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4caa2-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="4caa2-108">지정된 된 오프셋에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="4caa2-109">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="4caa2-110">코드 세그먼트의 상대 가상 주소 (RVA)을 가져옵니다이 `ICorDebugCode` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="4caa2-111">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="4caa2-112">디스어셈블리로 설정 된 지정된 된 함수에 대 한 모든 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="4caa2-113">이 메서드는 더 이상 사용 되지 않습니다. 사용 하 여 [icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="4caa2-114">GetEnCRemapSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="4caa2-115">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-115">Not implemented.</span></span>|  
|[<span data-ttu-id="4caa2-116">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="4caa2-117">이 연결 된 "ICorDebugFunction" 가져옵니다 `ICorDebugCode`합니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="4caa2-118">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="4caa2-119">MSIL 오프셋에서 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="4caa2-120">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="4caa2-121">이 표시 되는 이진 코드를 바이트 단위로 크기를 가져옵니다 `ICorDebugCode`합니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="4caa2-122">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="4caa2-123">코드의 버전을 식별 하는 1부터 번호를 가져옵니다이 `ICorDebugCode` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="4caa2-124">IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="4caa2-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="4caa2-125">나타내는 값을 가져옵니다 여부이 `ICorDebugCode` MSIL에 컴파일된 합니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4caa2-126">설명</span><span class="sxs-lookup"><span data-stu-id="4caa2-126">Remarks</span></span>  
 <span data-ttu-id="4caa2-127">`ICorDebugCode`MSIL 또는 네이티브 코드를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="4caa2-128">MSIL 코드를 나타내는 "ICorDebugFunction" 개체는 0 이나 1 점이 `ICorDebugCode` 관련 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="4caa2-129">네이티브 코드를 나타내는 "ICorDebugFunction" 개체 개수에 관계 없이 점이 `ICorDebugCode` 관련 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4caa2-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4caa2-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4caa2-131">Requirements</span></span>  
 <span data-ttu-id="4caa2-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4caa2-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4caa2-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4caa2-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4caa2-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4caa2-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4caa2-135">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4caa2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4caa2-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4caa2-136">See Also</span></span>  
    
 [<span data-ttu-id="4caa2-137">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4caa2-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="4caa2-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4caa2-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
