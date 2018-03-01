---
title: ICorDebugModule Interface1
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
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59c24d8305e71aac01843155b86fb54fb1e1263d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="ce439-102">ICorDebugModule Interface1</span><span class="sxs-lookup"><span data-stu-id="ce439-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="ce439-103">실행 파일 또는 동적 연결 라이브러리 (DLL) 중 하나는 공용 언어 런타임 (CLR) 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce439-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-104">Methods</span></span>  
  
|<span data-ttu-id="ce439-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-105">Method</span></span>|<span data-ttu-id="ce439-106">설명</span><span class="sxs-lookup"><span data-stu-id="ce439-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce439-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="ce439-108">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-108">Not implemented.</span></span>|  
|[<span data-ttu-id="ce439-109">EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="ce439-110">결정 여부는 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 이 모듈에 대 한 콜백을 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="ce439-111">EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="ce439-112">적시에 (JIT) 컴파일러가이 모듈 내에서 메서드에 대 한 디버깅 정보를 유지할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="ce439-113">GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="ce439-114">이 모듈에 대 한 포함 하는 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="ce439-115">GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="ce439-116">모듈의 기준 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="ce439-117">GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="ce439-118">메타 데이터에서의 ICorDebugClass를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="ce439-119">GetEditAndContinueSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="ce439-120">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-120">Deprecated.</span></span>|  
|[<span data-ttu-id="ce439-121">GetFunctionFromRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="ce439-122">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-122">Not implemented.</span></span>|  
|[<span data-ttu-id="ce439-123">GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="ce439-124">메타 데이터 토큰이 지정 된 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="ce439-125">GetGlobalVariableValue 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="ce439-126">지정된 된 전역 변수를 값 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="ce439-127">GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="ce439-128">모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="ce439-129">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="ce439-130">모듈의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="ce439-131">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="ce439-132">이 모듈을 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="ce439-133">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="ce439-134">모듈의 크기를 바이트 단위로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="ce439-135">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="ce439-136">이 모듈에 대 한 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="ce439-137">IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="ce439-138">동적 모듈 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="ce439-139">IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="ce439-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="ce439-140">이 모듈을 메모리에만 존재 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce439-141">설명</span><span class="sxs-lookup"><span data-stu-id="ce439-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce439-142">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce439-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce439-143">Requirements</span></span>  
 <span data-ttu-id="ce439-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce439-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce439-145">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce439-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce439-146">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce439-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce439-147">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce439-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce439-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce439-148">See Also</span></span>  
 [<span data-ttu-id="ce439-149">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce439-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="ce439-150">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce439-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
