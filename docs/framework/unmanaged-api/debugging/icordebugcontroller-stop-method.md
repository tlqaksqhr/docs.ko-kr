---
title: "ICorDebugController::Stop 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Stop
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a8699a54814b37cc03404b72330812f3eb2b2f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="2cf11-102">ICorDebugController::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="2cf11-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="2cf11-103">프로세스에서 관리 되는 코드를 실행 하는 모든 스레드에서 동시 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf11-104">구문</span><span class="sxs-lookup"><span data-stu-id="2cf11-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf11-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2cf11-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="2cf11-106">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cf11-107">설명</span><span class="sxs-lookup"><span data-stu-id="2cf11-107">Remarks</span></span>  
 <span data-ttu-id="2cf11-108">`Stop`프로세스의 코드가 관리 되는 실행 중인 모든 스레드에서 동시 중지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="2cf11-109">관리 전용 디버깅 세션 중에 관리 되지 않는 스레드 계속 실행할 수 있습니다 (하지만 관리 코드를 호출 하려고 할 때 차단 됩니다).</span><span class="sxs-lookup"><span data-stu-id="2cf11-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="2cf11-110">Interop 디버깅 세션 중 관리 되지 않는 스레드가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="2cf11-111">`dwTimeoutIgnored` 값은 현재 무시 되 고 무한 (-1)으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="2cf11-112">동시 중지 교착 상태로 인해 실패 하면 모든 스레드가 일시 중단 되 고 E_TIMEOUT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cf11-113">`Stop`디버깅 API의 동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="2cf11-114">때 `Stop` 반환 s_ok이 고, 프로세스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="2cf11-115">콜백이 없는 중지점의 수신기를 알리기 위해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="2cf11-116">디버거를 호출 해야 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 프로세스가 다시 시작을 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="2cf11-117">디버거 중지 카운터를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="2cf11-118">카운터가 0이 되 면 컨트롤러 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="2cf11-119">호출할 때마다 `Stop` 또는 디스패치 된 콜백을 카운터를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="2cf11-120">호출할 때마다 `ICorDebugController::Continue` 감소 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf11-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cf11-121">Requirements</span></span>  
 <span data-ttu-id="2cf11-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf11-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf11-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cf11-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cf11-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cf11-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cf11-125">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf11-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf11-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cf11-126">See Also</span></span>  
 
