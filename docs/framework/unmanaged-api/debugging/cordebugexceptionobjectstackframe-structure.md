---
title: CorDebugExceptionObjectStackFrame 구조체
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48b15429d40d3a69db52615592fc1697f385d319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403733"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="59ee8-102">CorDebugExceptionObjectStackFrame 구조체</span><span class="sxs-lookup"><span data-stu-id="59ee8-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="59ee8-103">예외 개체의 스택 프레임 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ee8-104">구문</span><span class="sxs-lookup"><span data-stu-id="59ee8-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="59ee8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="59ee8-105">Members</span></span>  
  
|<span data-ttu-id="59ee8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="59ee8-106">Member</span></span>|<span data-ttu-id="59ee8-107">설명</span><span class="sxs-lookup"><span data-stu-id="59ee8-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="59ee8-108">현재 프레임에 대 한 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="59ee8-109">현재 프레임에 대 한 명령 포인터 (EIP/RIP)의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="59ee8-110">현재 프레임에 대 한 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="59ee8-111">프레임은 마지막 외부 예외 프레임 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59ee8-112">설명</span><span class="sxs-lookup"><span data-stu-id="59ee8-112">Remarks</span></span>  
 <span data-ttu-id="59ee8-113">호출자에 게 더 이상 사용에서 되 면 ICorDebugModule 개체에 대 한 포인터를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59ee8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59ee8-114">Requirements</span></span>  
 <span data-ttu-id="59ee8-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59ee8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59ee8-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59ee8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59ee8-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59ee8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59ee8-118">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59ee8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ee8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59ee8-119">See Also</span></span>  
 [<span data-ttu-id="59ee8-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="59ee8-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="59ee8-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="59ee8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
