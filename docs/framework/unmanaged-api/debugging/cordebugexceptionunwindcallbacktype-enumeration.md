---
title: "CorDebugExceptionUnwindCallbackType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionUnwindCallbackType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionUnwindCallbackType
helpviewer_keywords: CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8528b2839c4972dd44f03db5f331acb672cfeb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="480f2-102">CorDebugExceptionUnwindCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="480f2-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="480f2-103">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="480f2-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="480f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="480f2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="480f2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="480f2-105">Members</span></span>  
  
|<span data-ttu-id="480f2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="480f2-106">Member</span></span>|<span data-ttu-id="480f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="480f2-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="480f2-108">해제 프로세스의 시작 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="480f2-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="480f2-109">예외를 가로 챘 습니다.</span><span class="sxs-lookup"><span data-stu-id="480f2-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="480f2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="480f2-110">Requirements</span></span>  
 <span data-ttu-id="480f2-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="480f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="480f2-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="480f2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="480f2-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="480f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="480f2-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="480f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480f2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="480f2-115">See Also</span></span>  
 [<span data-ttu-id="480f2-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="480f2-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
