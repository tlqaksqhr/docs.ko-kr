---
title: ICorDebugProcess Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e4e3854a850c9639e93c8db2ec8ccd567b242b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423171"
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="8f43e-102">ICorDebugProcess Interface1</span><span class="sxs-lookup"><span data-stu-id="8f43e-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="8f43e-103">관리 코드를 실행하는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="8f43e-104">이 인터페이스는 ICorDebugController의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f43e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-105">Methods</span></span>  
  
|<span data-ttu-id="8f43e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-106">Method</span></span>|<span data-ttu-id="8f43e-107">설명</span><span class="sxs-lookup"><span data-stu-id="8f43e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f43e-108">ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="8f43e-109">지정 된 스레드에 대해 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="8f43e-110">EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="8f43e-111">사용 하도록 설정 하 고 디버거에 로그 메시지를 보낼 수 없게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="8f43e-112">EnumerateAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="8f43e-113">모든 프로세스에서 응용 프로그램 도메인을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="8f43e-114">EnumerateObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="8f43e-115">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-115">Not implemented.</span></span>|  
|[<span data-ttu-id="8f43e-116">GetHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="8f43e-117">프로세스에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="8f43e-118">GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="8f43e-119">디버거의 내부 도우미 스레드가 대 한 운영 체제 (OS) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="8f43e-120">GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="8f43e-121">프로세스의 운영 체제 (OS) ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="8f43e-122">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="8f43e-123">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-123">Not implemented.</span></span>|  
|[<span data-ttu-id="8f43e-124">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="8f43e-125">Id를 가져옵니다에 지정 된 운영 체제 스레드가 ICorDebugThread 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="8f43e-126">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="8f43e-127">지정 된 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="8f43e-128">IsOSSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="8f43e-129">디버거가 프로세스를 중지의 결과 스레드가 일시 중단 된 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="8f43e-130">IsTransitionStub 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="8f43e-131">관리 코드에 전환 하는 스텁 내부 주소 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="8f43e-132">ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="8f43e-133">지정 된 로그 스위치의 심각도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="8f43e-134">ReadMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="8f43e-135">프로세스에서 메모리를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="8f43e-136">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="8f43e-137">지정 된 스레드에 대 한 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="8f43e-138">ThreadForFiberCookie 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="8f43e-139">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-139">Deprecated.</span></span>|  
|[<span data-ttu-id="8f43e-140">WriteMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="8f43e-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="8f43e-141">프로세스의 메모리 영역에 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f43e-142">설명</span><span class="sxs-lookup"><span data-stu-id="8f43e-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f43e-143">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f43e-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f43e-144">Requirements</span></span>  
 <span data-ttu-id="8f43e-145">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f43e-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f43e-146">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f43e-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f43e-147">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f43e-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f43e-148">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f43e-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f43e-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f43e-149">See Also</span></span>  
 [<span data-ttu-id="8f43e-150">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f43e-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="8f43e-151">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f43e-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
