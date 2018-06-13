---
title: ICorDebugController Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230488201b637c5a53f41dd4c3f204b37e8984fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411472"
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="9668d-102">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="9668d-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="9668d-103"><xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9668d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-104">Methods</span></span>  
  
|<span data-ttu-id="9668d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-105">Method</span></span>|<span data-ttu-id="9668d-106">설명</span><span class="sxs-lookup"><span data-stu-id="9668d-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="9668d-107">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="9668d-108">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="9668d-109">Continue 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="9668d-110">관리 되는 스레드를 호출한 후 실행을 계속 [icordebugcontroller:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="9668d-111">Detach 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="9668d-112">프로세스 또는 응용 프로그램 도메인에서 디버거를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="9668d-113">EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="9668d-114">프로세스에서 현재 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="9668d-115">HasQueuedCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="9668d-116">지정 된 스레드에 대 한 모든 관리 되는 콜백이 현재 대기 중인 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="9668d-117">IsRunning 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="9668d-118">프로세스의 스레드는 현재 실행에 자유롭게 수 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="9668d-119">SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="9668d-120">프로세스에서 모든 관리 되는 스레드의 디버그 상태를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="9668d-121">Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="9668d-122">프로세스에서 관리 되는 코드를 실행 하는 모든 스레드에서 동시 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="9668d-123">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="9668d-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="9668d-124">지정된 된 종료 코드가 사용 하 여 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9668d-125">설명</span><span class="sxs-lookup"><span data-stu-id="9668d-125">Remarks</span></span>  
 <span data-ttu-id="9668d-126">경우 `ICorDebugController` 는 프로세스를 제어 범위는 프로세스의 모든 스레드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="9668d-127">경우 `ICorDebugController` 되는 범위에 해당 특정 응용 프로그램 도메인의 스레드만 포함 응용 프로그램 도메인을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9668d-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9668d-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9668d-129">Requirements</span></span>  
 <span data-ttu-id="9668d-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9668d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9668d-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9668d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9668d-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9668d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9668d-133">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9668d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9668d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9668d-134">See Also</span></span>  
 [<span data-ttu-id="9668d-135">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9668d-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
