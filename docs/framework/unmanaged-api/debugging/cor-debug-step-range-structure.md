---
title: "COR_DEBUG_STEP_RANGE 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_DEBUG_STEP_RANGE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_DEBUG_STEP_RANGE
helpviewer_keywords: COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b1b7b26ea788683f9b322306c55a4b3945f342
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="5a5b8-102">COR_DEBUG_STEP_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="5a5b8-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="5a5b8-103">코드 범위에 대한 오프셋 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b8-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="5a5b8-104">이 구조에서 사용 되는 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5a5b8-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a5b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a5b8-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="5a5b8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5a5b8-106">Members</span></span>  
  
|<span data-ttu-id="5a5b8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5a5b8-107">Member</span></span>|<span data-ttu-id="5a5b8-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a5b8-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="5a5b8-109">범위의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b8-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="5a5b8-110">범위 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b8-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a5b8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a5b8-111">Requirements</span></span>  
 <span data-ttu-id="5a5b8-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5b8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a5b8-113">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="5a5b8-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5a5b8-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a5b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a5b8-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a5b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5b8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a5b8-116">See Also</span></span>  
 [<span data-ttu-id="5a5b8-117">StepRange 메서드</span><span class="sxs-lookup"><span data-stu-id="5a5b8-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="5a5b8-118">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="5a5b8-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="5a5b8-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="5a5b8-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
