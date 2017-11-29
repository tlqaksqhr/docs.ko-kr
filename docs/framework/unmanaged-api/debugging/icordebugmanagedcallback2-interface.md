---
title: "ICorDebugManagedCallback2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2
helpviewer_keywords: ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0d5b8ac63d200e54d25b58870089f6c062397186
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="31f43-102">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f43-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="31f43-103">디버거 예외 처리 및 MDA(관리 디버깅 도우미)를 지원하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="31f43-104">`ICorDebugManagedCallback2`논리적으로 확장 되는 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31f43-105">메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-105">Methods</span></span>  
  
|<span data-ttu-id="31f43-106">메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-106">Method</span></span>|<span data-ttu-id="31f43-107">설명</span><span class="sxs-lookup"><span data-stu-id="31f43-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31f43-108">ChangeConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="31f43-109">지정 된 연결과 관련 된 작업 집합이 변경 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="31f43-110">CreateConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="31f43-111">새 연결 만들어졌는지 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="31f43-112">DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="31f43-113">지정한 연결이 종료 되었습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="31f43-114">Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="31f43-115">예외 처리기에 대 한 검색이 시작 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="31f43-116">ExceptionUnwind 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="31f43-117">예외 해제 프로세스 중에 상태 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="31f43-118">FunctionRemapComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="31f43-119">편집 된 함수의 새 버전으로 코드 실행이 전환 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="31f43-120">FunctionRemapOpportunity 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="31f43-121">코드 실행 이전 버전의 편집된 된 함수에서 시퀀스 위치에 도달 했습니다 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="31f43-122">MDANotification 메서드</span><span class="sxs-lookup"><span data-stu-id="31f43-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="31f43-123">코드 실행에 관리 디버깅 도우미 (MDA) 메시지를 발생 하는 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31f43-124">설명</span><span class="sxs-lookup"><span data-stu-id="31f43-124">Remarks</span></span>  
 <span data-ttu-id="31f43-125">`ICorDebugManagedCallback2` 확장 인터페이스는 `ICorDebugManagedCallback` .NET Framework 버전 2.0에에서 도입 된 새 디버그 이벤트를 처리 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="31f43-126">디버거를 구현 해야 `ICorDebugManagedCallback2` .NET Framework 2.0 응용 프로그램을 디버깅 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="31f43-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="31f43-127">인스턴스 `ICorDebugManagedCallback` 또는 `ICorDebugManagedCallback2` 콜백 개체를 변수로 전달 되 [icordebug:: Setmanagedhandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31f43-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f43-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31f43-129">Requirements</span></span>  
 <span data-ttu-id="31f43-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31f43-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f43-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31f43-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f43-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f43-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31f43-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f43-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f43-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31f43-134">See Also</span></span>  
 [<span data-ttu-id="31f43-135">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="31f43-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="31f43-136">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f43-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="31f43-137">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31f43-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
