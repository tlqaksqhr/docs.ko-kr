---
title: "LoggingLevelEnum 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1f8bb53d53593073df7ef7aa095eeb3b9f8c632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="0b53f-102">LoggingLevelEnum 열거형</span><span class="sxs-lookup"><span data-stu-id="0b53f-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="0b53f-103">관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b53f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b53f-104">Syntax</span></span>  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="0b53f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0b53f-105">Members</span></span>  
  
|<span data-ttu-id="0b53f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0b53f-106">Member</span></span>|<span data-ttu-id="0b53f-107">설명</span><span class="sxs-lookup"><span data-stu-id="0b53f-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="0b53f-108">메시지 추적 수준이 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="0b53f-109">메시지는 추적 수준 1입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="0b53f-110">메시지는 추적 수준 2입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="0b53f-111">메시지는 추적 수준 3입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="0b53f-112">메시지는 추적 수준 4입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="0b53f-113">메시지는 상태 수준 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="0b53f-114">메시지는 상태 수준 1입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="0b53f-115">메시지는 상태 수준 2입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="0b53f-116">메시지는 상태 수준 3입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="0b53f-117">메시지는 상태 수준 4입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="0b53f-118">메시지는 경고 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="0b53f-119">메시지 오류 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="0b53f-120">메시지에는 심각한 오류 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b53f-121">설명</span><span class="sxs-lookup"><span data-stu-id="0b53f-121">Remarks</span></span>  
 <span data-ttu-id="0b53f-122">호출 하는 공용 언어 런타임 (CLR)는 [icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) 메서드 디버거에를 알리거나 관리 되는 스레드에서 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="0b53f-123">값을 전달 하는 CLR의 `LoggingLevelEnum` 열거형을 관리 되는 스레드 이벤트 로그에 작성 하는 메시지의 심각도 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b53f-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b53f-124">Requirements</span></span>  
 <span data-ttu-id="0b53f-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b53f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b53f-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b53f-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b53f-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b53f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b53f-128">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b53f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b53f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b53f-129">See Also</span></span>  
 <xref:System.Diagnostics.EventLog>  
 [<span data-ttu-id="0b53f-130">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="0b53f-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
