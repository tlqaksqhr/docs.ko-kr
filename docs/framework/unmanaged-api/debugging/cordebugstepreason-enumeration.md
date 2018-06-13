---
title: CorDebugStepReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71dcc34fd3489fc71cec4050b168548927833082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404533"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="7c815-102">CorDebugStepReason 열거형</span><span class="sxs-lookup"><span data-stu-id="7c815-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="7c815-103">개별 단계의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c815-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c815-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="7c815-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7c815-105">Members</span></span>  
  
|<span data-ttu-id="7c815-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7c815-106">Member</span></span>|<span data-ttu-id="7c815-107">설명</span><span class="sxs-lookup"><span data-stu-id="7c815-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="7c815-108">단계별 실행는 동일한 함수 내에서 정상적으로 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="7c815-109">단계별 함수가 반환 후 정상적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="7c815-110">단계별 실행이 새로 호출 된 함수의 시작 부분에 정상적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="7c815-111">예외가 발생 하 고 제어 예외 필터에 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="7c815-112">예외가 발생 하 고 제어 예외 처리기에 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="7c815-113">컨트롤은 인터셉터로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="7c815-114">단계를 완료 하기 전에 스레드가 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c815-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c815-115">Requirements</span></span>  
 <span data-ttu-id="7c815-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c815-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c815-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c815-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c815-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c815-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c815-119">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c815-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c815-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c815-120">See Also</span></span>  
 [<span data-ttu-id="7c815-121">StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="7c815-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="7c815-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="7c815-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
