---
title: "ICorDebugManagedCallback::BreakpointSetError 메서드"
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
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff1d3ee5d8bde9f2c1a6d3b97c42edb0b2deb6df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="20c95-102">ICorDebugManagedCallback::BreakpointSetError 메서드</span><span class="sxs-lookup"><span data-stu-id="20c95-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="20c95-103">공용 언어 런타임 함수를 just-in-time (JIT) 컴파일 전에 설정 된 중단점을 정확 하 게 바인딩할 수 없음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c95-104">구문</span><span class="sxs-lookup"><span data-stu-id="20c95-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20c95-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20c95-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="20c95-106">[in] 바인딩 해제 된 중단점을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="20c95-107">[in] 바인딩되지 않은 중단점을 포함 하는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="20c95-108">[in] 바인딩 해제 된 중단점을 나타내는 ICorDebugBreakpoint 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="20c95-109">[in] 이 오류를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20c95-110">설명</span><span class="sxs-lookup"><span data-stu-id="20c95-110">Remarks</span></span>  
 <span data-ttu-id="20c95-111">지정 된 중단점을 적중 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="20c95-112">디버거는 비활성화 하 고 다시 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c95-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20c95-113">Requirements</span></span>  
 <span data-ttu-id="20c95-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20c95-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c95-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20c95-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20c95-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c95-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20c95-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c95-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c95-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20c95-118">See Also</span></span>  
 [<span data-ttu-id="20c95-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20c95-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
