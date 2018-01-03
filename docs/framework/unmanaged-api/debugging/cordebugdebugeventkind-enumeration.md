---
title: "CorDebugDebugEventKind 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDebugEventKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90cd2b8d02cb1d16e4932ffdcc3c9b02dc71541a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="4a4a0-102">CorDebugDebugEventKind 열거형</span><span class="sxs-lookup"><span data-stu-id="4a4a0-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="4a4a0-103">정보를 가져올 디코딩되는 이벤트의 유형을 나타냅니다는 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a4a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a4a0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="4a4a0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4a4a0-105">Members</span></span>  
  
|<span data-ttu-id="4a4a0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4a4a0-106">Member</span></span>|<span data-ttu-id="4a4a0-107">설명</span><span class="sxs-lookup"><span data-stu-id="4a4a0-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="4a4a0-108">모듈 로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="4a4a0-109">모듈 언로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="4a4a0-110">첫째 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="4a4a0-111">첫째 사용자 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="4a4a0-112">`catch` 처리기가 있는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="4a4a0-113">처리되지 않은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a4a0-114">설명</span><span class="sxs-lookup"><span data-stu-id="4a4a0-114">Remarks</span></span>  
 <span data-ttu-id="4a4a0-115">멤버는 `CorDebugDebugEventKind` 열거형이 호출 하 여 반환 된 [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a4a0-116">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a4a0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a4a0-117">Requirements</span></span>  
 <span data-ttu-id="4a4a0-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4a0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a4a0-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a4a0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a4a0-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a4a0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a4a0-121">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a4a0-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4a0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a4a0-122">See Also</span></span>  
 [<span data-ttu-id="4a4a0-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="4a4a0-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
