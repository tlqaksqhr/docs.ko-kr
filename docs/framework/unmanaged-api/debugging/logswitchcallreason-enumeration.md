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
ms.workload: dotnet
ms.openlocfilehash: 3dcd91001dfd823416b08ba49ba4ed12a2c4d058
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="6f9ce-102">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="6f9ce-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="6f9ce-103">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ce-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f9ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f9ce-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="6f9ce-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6f9ce-105">Members</span></span>  
  
|<span data-ttu-id="6f9ce-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6f9ce-106">Member</span></span>|<span data-ttu-id="6f9ce-107">설명</span><span class="sxs-lookup"><span data-stu-id="6f9ce-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="6f9ce-108">디버깅/추적 스위치를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ce-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="6f9ce-109">디버깅/추적 스위치 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ce-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="6f9ce-110">디버깅/추적 스위치를 삭제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ce-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f9ce-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f9ce-111">Requirements</span></span>  
 <span data-ttu-id="6f9ce-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f9ce-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f9ce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f9ce-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f9ce-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f9ce-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f9ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9ce-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f9ce-116">See Also</span></span>  
 [<span data-ttu-id="6f9ce-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6f9ce-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
