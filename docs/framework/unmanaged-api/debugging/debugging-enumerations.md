---
title: 디버깅 열거형
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b81e7c2ffabdee78af34d00c48fb29c7525dea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410470"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="6212a-102">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-102">Debugging Enumerations</span></span>
<span data-ttu-id="6212a-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 열거형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6212a-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6212a-104">In This Section</span></span>  
 [<span data-ttu-id="6212a-105">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="6212a-106">사용 되는 값을 제공 된 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6212a-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="6212a-107">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="6212a-108">메모리 영역에 대 한 호출을 나타냅니다는 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메서드가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="6212a-109">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="6212a-110">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="6212a-111">CorDebugBlockingReason 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="6212a-112">지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="6212a-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="6212a-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="6212a-114">호출 체인의 시작 이유를 하나 이상 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="6212a-115">CorDebugCodeInvokeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="6212a-116">내보낸 함수가 관리 코드를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="6212a-117">CorDebugCodeInvokePurpose 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="6212a-118">내보낸 함수가 관리 코드를 호출하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="6212a-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="6212a-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="6212a-120">에 대 한 호출에서 사용할 수 있는 추가 디버깅 옵션을 제공 된 [icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6212a-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="6212a-121">CorDebugDebugEventKind 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="6212a-122">정보를 가져올 디코딩되는 이벤트의 유형을 나타냅니다는 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6212a-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="6212a-123">CorDebugDecodeEventFlagsWindows 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="6212a-124">Windows 플랫폼에서 디버그 이벤트에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="6212a-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="6212a-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="6212a-126">수행 되는 콜백의 형식을 나타냅니다는 [icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="6212a-127">CorDebugExceptionFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="6212a-128">예외에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="6212a-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="6212a-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="6212a-130">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="6212a-131">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="6212a-132">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="6212a-133">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="6212a-134">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="6212a-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="6212a-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="6212a-136">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="6212a-137">CorDebugIlToNativeMappingTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="6212a-138">기본 명령의 특정 범위가 특수 코드 영역에 해당하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="6212a-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="6212a-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="6212a-140">한 단계씩 실행할 수 있는 코드 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="6212a-141">CorDebugInterfaceVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="6212a-142">특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="6212a-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="6212a-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="6212a-144">스택 프레임 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="6212a-145">CorDebugJITCompilerFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="6212a-146">관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="6212a-147">CorDebugJITCompilerFlagsDeprecated 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="6212a-148">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-148">Obsolete.</span></span> <span data-ttu-id="6212a-149">사용 하 여는 `CORDEBUG_JIT_DEFAULT` 의 멤버는 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 열거형 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="6212a-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="6212a-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="6212a-151">IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="6212a-152">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="6212a-153">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="6212a-154">CorDebugNGenPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="6212a-155">디버거가 네이티브 이미지 캐시에서 네이티브(NGen) 이미지를 로드하는지 여부를 결정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="6212a-156">CorDebugPlatform 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="6212a-157">사용 되는 대상 플랫폼 값을 제공 된 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6212a-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="6212a-158">CorDebugRecordFormat 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="6212a-159">네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="6212a-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="6212a-160">CorDebugRegister</span></span>  
 <span data-ttu-id="6212a-161">지정한 프로세서 아키텍처에 연결된 레지스터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="6212a-162">CorDebugSetContextFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="6212a-163">컨텍스트가 스택의 활성(리프) 프레임에서 가져온 것인지 아니면 다른 프레임에서 해제하여 계산되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="6212a-164">CorDebugStateChange 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="6212a-165">프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="6212a-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="6212a-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="6212a-167">개별 단계의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="6212a-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="6212a-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="6212a-169">디버깅을 위한 스레드 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="6212a-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="6212a-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="6212a-171">스텝퍼에 의해 코드 실행에서 중지를 트리거할 수 있는 매핑되지 않은 코드 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="6212a-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="6212a-172">CorDebugUserState</span></span>  
 <span data-ttu-id="6212a-173">스레드의 사용자 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="6212a-174">CorGCReferenceType 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="6212a-175">가비지가 수집될 개체의 소스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="6212a-176">ILCodeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="6212a-177">디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수나 코드에 액세스할 수 있는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="6212a-178">LoggingLevelEnum 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="6212a-179">관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="6212a-180">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="6212a-181">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="6212a-182">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="6212a-183">기본 위치에 대 한 유형을 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="6212a-184">WriteableMetadataUpdateMode 열거형</span><span class="sxs-lookup"><span data-stu-id="6212a-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="6212a-185">메타데이터에 대한 메모리 내 업데이트가 디버거에 표시되는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6212a-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6212a-186">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6212a-186">Related Sections</span></span>  
 [<span data-ttu-id="6212a-187">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="6212a-187">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="6212a-188">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6212a-188">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="6212a-189">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6212a-189">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="6212a-190">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="6212a-190">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
