---
title: "ICorDebugExceptionDebugEvent::GetNativeIP 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 616f0a9787220aba0cc4d460c80b856076e1e437
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="a134b-102">ICorDebugExceptionDebugEvent::GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="a134b-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="a134b-103">이 예외 디버그 이벤트에 대한 네이티브 명령 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a134b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a134b-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a134b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a134b-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="a134b-106">[out] 이 예외 디버그 이벤트의 명령 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="a134b-107">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a134b-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a134b-108">설명</span><span class="sxs-lookup"><span data-stu-id="a134b-108">Remarks</span></span>  
 <span data-ttu-id="a134b-109">이 명령 포인터의 의미는 다음 표와 같이 이벤트 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a134b-110">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a134b-110">Event type</span></span>|<span data-ttu-id="a134b-111">`pStackPointer` 값의 의미</span><span class="sxs-lookup"><span data-stu-id="a134b-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="a134b-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a134b-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="a134b-113">오류가 발생한 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="a134b-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a134b-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="a134b-115">로 표시 된 프레임의 코드 주소는 [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) 메서드 예외가 발생 하는 경우 실행이 다시 시작 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="a134b-116">예외로 인해 `try/catch/finally` 절의 catch 블록과 같은 다른 코드가 이 프레임에서 실행되거나 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="a134b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="a134b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="a134b-118">코드 주소 `catch` 처리기 실행으로 지정 된 프레임에서 시작 됩니다는 [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a134b-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="a134b-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="a134b-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="a134b-120">`pIP`가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="a134b-121">이벤트 형식이에서 표시 되는 [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a134b-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a134b-122">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a134b-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a134b-123">Requirements</span></span>  
 <span data-ttu-id="a134b-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a134b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a134b-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a134b-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a134b-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a134b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a134b-127">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a134b-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a134b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a134b-128">See Also</span></span>  
 [<span data-ttu-id="a134b-129">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a134b-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="a134b-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a134b-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
