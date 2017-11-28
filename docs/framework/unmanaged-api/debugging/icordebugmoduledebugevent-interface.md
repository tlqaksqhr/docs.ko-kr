---
title: "ICorDebugModuleDebugEvent 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dced93ab39529ec57fb6fb99603a197fb957be8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="b4e9f-102">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4e9f-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="b4e9f-103">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4e9f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b4e9f-104">Methods</span></span>  
  
|<span data-ttu-id="b4e9f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b4e9f-105">Method</span></span>|<span data-ttu-id="b4e9f-106">설명</span><span class="sxs-lookup"><span data-stu-id="b4e9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4e9f-107">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="b4e9f-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="b4e9f-108">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4e9f-109">설명</span><span class="sxs-lookup"><span data-stu-id="b4e9f-109">Remarks</span></span>  
 <span data-ttu-id="b4e9f-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 및 [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트 유형을이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4e9f-111">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="b4e9f-112">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4e9f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4e9f-113">Requirements</span></span>  
 <span data-ttu-id="b4e9f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e9f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e9f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4e9f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4e9f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4e9f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4e9f-117">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e9f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e9f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4e9f-118">See Also</span></span>  
 [<span data-ttu-id="b4e9f-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4e9f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b4e9f-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="b4e9f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
