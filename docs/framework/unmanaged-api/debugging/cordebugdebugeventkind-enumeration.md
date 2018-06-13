---
title: CorDebugDebugEventKind 열거형
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f2f5af86e210493cd8ba0eb8afe10d22b84b18c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408010"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="38a8b-102">CorDebugDebugEventKind 열거형</span><span class="sxs-lookup"><span data-stu-id="38a8b-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="38a8b-103">정보를 가져올 디코딩되는 이벤트의 유형을 나타냅니다는 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="38a8b-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="38a8b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="38a8b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="38a8b-105">Members</span></span>  
  
|<span data-ttu-id="38a8b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="38a8b-106">Member</span></span>|<span data-ttu-id="38a8b-107">설명</span><span class="sxs-lookup"><span data-stu-id="38a8b-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="38a8b-108">모듈 로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="38a8b-109">모듈 언로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="38a8b-110">첫째 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="38a8b-111">첫째 사용자 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="38a8b-112">`catch` 처리기가 있는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="38a8b-113">처리되지 않은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38a8b-114">설명</span><span class="sxs-lookup"><span data-stu-id="38a8b-114">Remarks</span></span>  
 <span data-ttu-id="38a8b-115">멤버는 `CorDebugDebugEventKind` 열거형이 호출 하 여 반환 된 [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="38a8b-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38a8b-116">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a8b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38a8b-117">Requirements</span></span>  
 <span data-ttu-id="38a8b-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38a8b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a8b-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38a8b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38a8b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38a8b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38a8b-121">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a8b-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a8b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38a8b-122">See Also</span></span>  
 [<span data-ttu-id="38a8b-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="38a8b-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
