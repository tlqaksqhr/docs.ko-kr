---
title: "CLR_DEBUGGING_PROCESS_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_PROCESS_FLAGS
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords: CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5040b1e1eb7ec4bd814329de156fcdfeb9c383c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="7e437-102">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="7e437-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="7e437-103">사용 되는 값을 제공 된 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="7e437-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e437-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e437-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="7e437-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7e437-105">Members</span></span>  
  
|<span data-ttu-id="7e437-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7e437-106">Member</span></span>|<span data-ttu-id="7e437-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e437-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="7e437-108">이 런타임 보낼 catch 업 아닌 관리 되는 디버거 이벤트를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="7e437-109">따라잡기 및 catch 업 비 이벤트 간의 차이 대 한 설명 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e437-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="7e437-110">보류 중인 관리 되는 이벤트는 한 <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e437-111">설명</span><span class="sxs-lookup"><span data-stu-id="7e437-111">Remarks</span></span>  
 <span data-ttu-id="7e437-112">후속 이벤트는 프로세스, 응용 프로그램 도메인, 어셈블리, 모듈 및 프로세스에 연결에 디버거가 현재 상태로 전환 하는 스레드 만들기 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="7e437-113">비 catch 업 이벤트도 표시 하는 `CLR_DEBUGGING_MANAGED_EVENT_PENDING` 플래그입니다. 모든 다른 디버거 이벤트, 예외 등을 포함 하 고 관리 디버깅 도우미 (MDA) 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="7e437-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` 플래그를 사용 하면 런타임 예외를 종료 하 고 취소할 수 있는 관리 되는 디버거가 연결 요청을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e437-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e437-115">Requirements</span></span>  
 <span data-ttu-id="7e437-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e437-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e437-117">**헤더:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="7e437-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="7e437-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e437-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e437-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e437-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e437-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e437-120">See Also</span></span>  
 [<span data-ttu-id="7e437-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="7e437-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="7e437-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="7e437-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
