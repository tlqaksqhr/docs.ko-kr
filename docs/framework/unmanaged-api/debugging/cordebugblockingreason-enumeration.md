---
title: CorDebugBlockingReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5e1267b619d5900ed9af55dd6079a8f38d6550
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406902"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="2f2f4-102">CorDebugBlockingReason 열거형</span><span class="sxs-lookup"><span data-stu-id="2f2f4-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="2f2f4-103">지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f2f4-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="2f2f4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2f2f4-105">Members</span></span>  
  
|<span data-ttu-id="2f2f4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2f2f4-106">Member</span></span>|<span data-ttu-id="2f2f4-107">설명</span><span class="sxs-lookup"><span data-stu-id="2f2f4-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="2f2f4-108">내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="2f2f4-109">스레드 임계 연결 된 개체에 대 한 모니터 잠금과 획득 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="2f2f4-110">중 하나를 호출 하는 경우 일반적으로 발생이 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="2f2f4-111">스레드가 개체에 대 한 모니터 잠금과와 연결 하는 이벤트를 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="2f2f4-112">중 하나를 호출 하는 경우 일반적으로 발생이 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` 메서드.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f2f4-113">설명</span><span class="sxs-lookup"><span data-stu-id="2f2f4-113">Remarks</span></span>  
 <span data-ttu-id="2f2f4-114">때는 `BLOCKING_MONITOR_CRITICAL_SECTION` 또는 `BLOCKING_MONITOR_EVENT` 멤버에 사용 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조는 `pBlockingObject` 구조 가리키는 입력 되 고 개체를 나타내는 "ICorDebugValue" 인터페이스의 멤버 .</span><span class="sxs-lookup"><span data-stu-id="2f2f4-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="2f2f4-115">구현 보장도 [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f2f4-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f2f4-116">Requirements</span></span>  
 <span data-ttu-id="2f2f4-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2f4-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f2f4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f2f4-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f2f4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f2f4-120">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f2f4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2f4-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f2f4-121">See Also</span></span>  
 [<span data-ttu-id="2f2f4-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="2f2f4-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="2f2f4-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="2f2f4-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
