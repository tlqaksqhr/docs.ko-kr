---
title: "ICorDebugManagedCallback::DebuggerError 메서드"
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
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc92bc6a1718d9d3505443e5b13786d1a359481f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="bb2f5-102">ICorDebugManagedCallback::DebuggerError 메서드</span><span class="sxs-lookup"><span data-stu-id="bb2f5-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="bb2f5-103">공용 언어 런타임 (CLR)의 이벤트를 처리 하는 동안 오류가 발생 했습니다는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb2f5-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb2f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb2f5-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="bb2f5-106">[in] 이벤트가 발생 한 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="bb2f5-107">[in] 이벤트 처리기에서 반환 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="bb2f5-108">[in] CLR 오류를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb2f5-109">설명</span><span class="sxs-lookup"><span data-stu-id="bb2f5-109">Remarks</span></span>  
 <span data-ttu-id="bb2f5-110">프로세스 오류의 성격에 따라 통과 모드로 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="bb2f5-111">`DebugError` 콜백은 있도록 오류 메시지 사용할 수 있는 사용자에 게 디버깅 서비스 오류로 인해 비활성화 되었음을 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="bb2f5-112">[Icordebugprocess:: Getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) 호출을 포함 한 다른 모든 메서드를 안전한 [icordebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="bb2f5-113">디버거는 프로세스를 종료 하기 위해 운영 체제 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb2f5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb2f5-114">Requirements</span></span>  
 <span data-ttu-id="bb2f5-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb2f5-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb2f5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb2f5-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb2f5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb2f5-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb2f5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2f5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb2f5-119">See Also</span></span>  
 [<span data-ttu-id="bb2f5-120">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb2f5-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
