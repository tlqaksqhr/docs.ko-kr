---
title: ICorDebugDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a2543a9629c60fde2b2f14c11898ba3e9df3c82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419314"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="5b9a1-102">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b9a1-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="5b9a1-103">모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b9a1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5b9a1-104">Methods</span></span>  
  
|<span data-ttu-id="5b9a1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5b9a1-105">Method</span></span>|<span data-ttu-id="5b9a1-106">설명</span><span class="sxs-lookup"><span data-stu-id="5b9a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b9a1-107">GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="5b9a1-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="5b9a1-108">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="5b9a1-109">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="5b9a1-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="5b9a1-110">이벤트가 발생한 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b9a1-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b9a1-111">Remarks</span></span>  
 <span data-ttu-id="5b9a1-112">다음 인터페이스는 `ICorDebugDebugEvent` 인터페이스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="5b9a1-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5b9a1-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="5b9a1-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5b9a1-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="5b9a1-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5b9a1-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b9a1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b9a1-117">Requirements</span></span>  
 <span data-ttu-id="5b9a1-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9a1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b9a1-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b9a1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b9a1-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b9a1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b9a1-121">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b9a1-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9a1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b9a1-122">See Also</span></span>  
 [<span data-ttu-id="5b9a1-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b9a1-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5b9a1-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="5b9a1-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
