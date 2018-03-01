---
title: "ICorDebugProcess::GetHelperThreadID 메서드"
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
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03e801cb58b8f5c3f658085fcee4288278e545c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="1663c-102">ICorDebugProcess::GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="1663c-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="1663c-103">디버거의 내부 도우미 스레드가의 운영 체제 (OS) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1663c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1663c-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1663c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1663c-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="1663c-106">[out] 운영 체제에 대 한 포인터 스레드 디버거의 내부 도우미 스레드가의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1663c-107">설명</span><span class="sxs-lookup"><span data-stu-id="1663c-107">Remarks</span></span>  
 <span data-ttu-id="1663c-108">관리 되는 관리 되지 않는 디버깅 하는 동안는 디버거의 배치 디버거가 중단점에 도달할 경우 지정한 ID 가진 스레드가 계속 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="1663c-109">디버거가이 스레드는 사용자 로부터 숨길 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="1663c-110">도우미 스레드가 아직 프로세스에 있는 경우는 `GetHelperThreadID` 메서드에 0을 반환 합니다 \*`pThreadID`합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="1663c-111">시간이 지남에 따라 변경 될 수 있으므로 도우미 스레드의 스레드 ID를 캐시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="1663c-112">모든 중지 이벤트에서 스레드 ID를 다시 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="1663c-113">디버거 도우미 스레드의 스레드 ID에 수정 될 모든 관리 되지 않는 [icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 이벤트, 디버거 도우미 스레드에서의 스레드 ID를 확인 하 고 사용자 로부터 숨길 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="1663c-114">관리 되지 않는 동안 도우미 스레드로 식별 되는 스레드 `ICorDebugManagedCallback::CreateThread` 이벤트 관리 되는 사용자 코드를 실행 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1663c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1663c-115">Requirements</span></span>  
 <span data-ttu-id="1663c-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1663c-117">**헤더:** CorDebug.idl 합니다.</span><span class="sxs-lookup"><span data-stu-id="1663c-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="1663c-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1663c-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="1663c-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1663c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1663c-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1663c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
