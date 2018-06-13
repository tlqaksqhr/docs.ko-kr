---
title: CorDebugExceptionCallbackType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fc0919a7c05bfcbfb4b54dd0b618564f019f3fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407822"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="3880d-102">CorDebugExceptionCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="3880d-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="3880d-103">수행 되는 콜백의 형식을 나타냅니다는 [icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3880d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3880d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="3880d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3880d-105">Members</span></span>  
  
|<span data-ttu-id="3880d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3880d-106">Member</span></span>|<span data-ttu-id="3880d-107">설명</span><span class="sxs-lookup"><span data-stu-id="3880d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="3880d-108">예외가 throw 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="3880d-109">예외 종료 프로세스가 사용자 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="3880d-110">찾을 예외 종료 프로세스가 `catch` 사용자 코드에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="3880d-111">예외 처리 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3880d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3880d-112">Requirements</span></span>  
 <span data-ttu-id="3880d-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3880d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3880d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3880d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3880d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3880d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3880d-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3880d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3880d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3880d-117">See Also</span></span>  
 [<span data-ttu-id="3880d-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="3880d-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
