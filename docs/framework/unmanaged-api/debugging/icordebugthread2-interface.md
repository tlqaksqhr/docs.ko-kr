---
title: ICorDebugThread2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2
helpviewer_keywords: ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3a554d075adb56294e4693b234ce22735fb982
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="24a0e-102">ICorDebugThread2 Interface1</span><span class="sxs-lookup"><span data-stu-id="24a0e-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="24a0e-103">ICorDebugThread 인터페이스를 논리적으로 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24a0e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-104">Methods</span></span>  
  
|<span data-ttu-id="24a0e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-105">Method</span></span>|<span data-ttu-id="24a0e-106">설명</span><span class="sxs-lookup"><span data-stu-id="24a0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24a0e-107">GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="24a0e-108">COR_ACTIVE_FUNCTION 인스턴스 스레드 프레임에서 현재 함수에 대 한 데이터가 포함 된 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="24a0e-109">GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="24a0e-110">이 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="24a0e-111">GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="24a0e-112">이 대 한 작업 id를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="24a0e-113">GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="24a0e-114">이 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="24a0e-115">InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="24a0e-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="24a0e-116">디버거에서를 스레드에서 현재 예외를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24a0e-117">설명</span><span class="sxs-lookup"><span data-stu-id="24a0e-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24a0e-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24a0e-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24a0e-119">Requirements</span></span>  
 <span data-ttu-id="24a0e-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="24a0e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a0e-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24a0e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24a0e-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24a0e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24a0e-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24a0e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a0e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24a0e-124">See Also</span></span>  
 [<span data-ttu-id="24a0e-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24a0e-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
