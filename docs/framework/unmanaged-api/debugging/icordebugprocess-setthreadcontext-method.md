---
title: "ICorDebugProcess::SetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="10749-102">ICorDebugProcess::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="10749-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="10749-103">이 프로세스에서 지정 된 스레드의 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10749-104">구문</span><span class="sxs-lookup"><span data-stu-id="10749-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10749-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10749-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="10749-106">[in] 컨텍스트를 설정 하는 대 한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10749-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="10749-107">[in] `context` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="10749-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="10749-108">[in] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="10749-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="10749-109">컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10749-110">설명</span><span class="sxs-lookup"><span data-stu-id="10749-110">Remarks</span></span>  
 <span data-ttu-id="10749-111">디버거에서 Win32 대신이 메서드를 호출 해야 `SetThreadContext` 는 스레드는 실제로는 해당 컨텍스트가 일시적으로 변경 된 "도용된" 상태에 있을 때문에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="10749-112">스레드가 네이티브 코드에 있을 때만이 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="10749-113">사용 하 여 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 관리 코드의 스레드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="10749-114">밴드의 범위를 벗어난 (OOB) 디버그 이벤트 중의 스레드 컨텍스트를 수정할 필요가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="10749-115">전달 되는 데이터는 현재 플랫폼에 대 한 상황에 맞는 구조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="10749-116">이 메서드는 제대로 사용 하지 않으면 런타임을 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10749-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10749-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10749-117">Requirements</span></span>  
 <span data-ttu-id="10749-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10749-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10749-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10749-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10749-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10749-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10749-121">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10749-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
