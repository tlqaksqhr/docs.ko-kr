---
title: "CorDebugIntercept 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIntercept
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIntercept
helpviewer_keywords: CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7d34b5f1bdff7a7089d780645b91503a8464849
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="0dcfc-102">CorDebugIntercept 열거형</span><span class="sxs-lookup"><span data-stu-id="0dcfc-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="0dcfc-103">가로챌 수 있는(즉, 한 단계씩 실행할 수 있는) 코드 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dcfc-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dcfc-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="0dcfc-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0dcfc-105">Members</span></span>  
  
|<span data-ttu-id="0dcfc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0dcfc-106">Member</span></span>|<span data-ttu-id="0dcfc-107">설명</span><span class="sxs-lookup"><span data-stu-id="0dcfc-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="0dcfc-108">코드를 가로챌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="0dcfc-109">생성자를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="0dcfc-110">예외 필터를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="0dcfc-111">보안을 적용 하는 코드를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="0dcfc-112">컨텍스트 정책을 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="0dcfc-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="0dcfc-114">모든 코드를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dcfc-115">설명</span><span class="sxs-lookup"><span data-stu-id="0dcfc-115">Remarks</span></span>  
 <span data-ttu-id="0dcfc-116">사용 하 여는 [icordebugstepper:: Setinterceptmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) 메서드를 가로챌 수 있는 코드 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dcfc-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dcfc-117">Requirements</span></span>  
 <span data-ttu-id="0dcfc-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dcfc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dcfc-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dcfc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dcfc-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dcfc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dcfc-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dcfc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcfc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dcfc-122">See Also</span></span>  
 [<span data-ttu-id="0dcfc-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="0dcfc-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
