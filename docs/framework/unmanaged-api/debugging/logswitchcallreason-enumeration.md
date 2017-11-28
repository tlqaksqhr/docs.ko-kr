---
title: "LogSwitchCallReason 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LogSwitchCallReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: LogSwitchCallReason
helpviewer_keywords: LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 937b26efa79605b585c420db608a938b3ee71f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="95ea4-102">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="95ea4-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="95ea4-103">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95ea4-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ea4-104">구문</span><span class="sxs-lookup"><span data-stu-id="95ea4-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="95ea4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="95ea4-105">Members</span></span>  
  
|<span data-ttu-id="95ea4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="95ea4-106">Member</span></span>|<span data-ttu-id="95ea4-107">설명</span><span class="sxs-lookup"><span data-stu-id="95ea4-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="95ea4-108">디버깅/추적 스위치를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="95ea4-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="95ea4-109">디버깅/추적 스위치 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95ea4-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="95ea4-110">디버깅/추적 스위치를 삭제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="95ea4-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95ea4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95ea4-111">Requirements</span></span>  
 <span data-ttu-id="95ea4-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95ea4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ea4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95ea4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95ea4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95ea4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95ea4-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ea4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ea4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95ea4-116">See Also</span></span>  
 [<span data-ttu-id="95ea4-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="95ea4-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
