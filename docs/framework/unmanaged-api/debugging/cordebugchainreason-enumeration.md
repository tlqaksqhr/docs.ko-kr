---
title: "CorDebugChainReason 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugChainReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugChainReason
helpviewer_keywords: CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1951983c9d167862169bd6178dc65693d724dc0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="c994a-102">CorDebugChainReason 열거형</span><span class="sxs-lookup"><span data-stu-id="c994a-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="c994a-103">호출 체인의 시작 이유를 하나 이상 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c994a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c994a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c994a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c994a-105">Members</span></span>  
  
|<span data-ttu-id="c994a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c994a-106">Member</span></span>|<span data-ttu-id="c994a-107">설명</span><span class="sxs-lookup"><span data-stu-id="c994a-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="c994a-108">호출 체인이 시작되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="c994a-109">생성자를 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="c994a-110">예외 필터를 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="c994a-111">보안을 적용하는 코드를 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="c994a-112">컨텍스트 정책을 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="c994a-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="c994a-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="c994a-115">스레드 실행 시작을 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="c994a-116">관리 코드에 대한 입력을 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="c994a-117">비관리 코드에 대한 입력을 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="c994a-118">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="c994a-119">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="c994a-120">함수 평가를 통해 체인이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c994a-121">설명</span><span class="sxs-lookup"><span data-stu-id="c994a-121">Remarks</span></span>  
 <span data-ttu-id="c994a-122">사용 하 여는 [icordebugchain:: Getreason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) 메서드를 호출 체인의 시작에 대 한 이유를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c994a-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c994a-123">Requirements</span></span>  
 <span data-ttu-id="c994a-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c994a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c994a-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c994a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c994a-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c994a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c994a-127">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c994a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c994a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c994a-128">See Also</span></span>  
 [<span data-ttu-id="c994a-129">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="c994a-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
