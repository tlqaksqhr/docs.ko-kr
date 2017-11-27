---
title: "CorDebugBlockingObject 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingObject Structure
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingObject
helpviewer_keywords: CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c47735565c960c2600f7274d0d59d5a6ec6c178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="cda35-102">CorDebugBlockingObject 구조체</span><span class="sxs-lookup"><span data-stu-id="cda35-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="cda35-103">스레드가 차단 되는 특별 한 이유가 스레드가 차단 되는 개체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda35-104">구문</span><span class="sxs-lookup"><span data-stu-id="cda35-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="cda35-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cda35-105">Members</span></span>  
  
|<span data-ttu-id="cda35-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cda35-106">Member</span></span>|<span data-ttu-id="cda35-107">설명</span><span class="sxs-lookup"><span data-stu-id="cda35-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="cda35-108">스레드가 차단 되어 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="cda35-109">이 개체는 현재 동기화 된 상태의 기간에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="cda35-110">스레드가 각각 두를 동일한 동기화 된 상태에서 동일한 개체에 차단 하는 경우 예상 된 [icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) 메서드를 같은 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="cda35-111">그러나 인터페이스 수 또는 포인터에 해당 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="cda35-112">작업을 차단 하기 전에 시간을 밀리초 단위로 시간 제한 또는 제한 시간이 초과 되지 않음을 나타내는 INFINITE 값 됩니다. 시간 제한 값은 남아 있는 시간이 아닌 차단 작업에 대 한 시간의 총 길이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="cda35-113">이 개체에서 스레드가 차단 되는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda35-114">설명</span><span class="sxs-lookup"><span data-stu-id="cda35-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda35-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cda35-115">Requirements</span></span>  
 <span data-ttu-id="cda35-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cda35-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda35-117">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="cda35-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="cda35-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda35-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cda35-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda35-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda35-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cda35-120">See Also</span></span>  
 [<span data-ttu-id="cda35-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="cda35-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="cda35-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="cda35-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
