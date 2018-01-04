---
title: "ICorDebugVirtualUnwinder 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 936df5c3d913a2ee5a1648906fb3ece2751d8ef5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="80907-102">ICorDebugVirtualUnwinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80907-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="80907-103">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80907-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80907-104">메서드</span><span class="sxs-lookup"><span data-stu-id="80907-104">Methods</span></span>  
  
|<span data-ttu-id="80907-105">메서드</span><span class="sxs-lookup"><span data-stu-id="80907-105">Method</span></span>|<span data-ttu-id="80907-106">name</span><span class="sxs-lookup"><span data-stu-id="80907-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="80907-107">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="80907-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="80907-108">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80907-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="80907-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="80907-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="80907-110">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="80907-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80907-111">설명</span><span class="sxs-lookup"><span data-stu-id="80907-111">Remarks</span></span>  
 <span data-ttu-id="80907-112">`ICorDebugVirtualUnwinder` 인터페이스의 멤버는 스택 해제에 도움이 되도록 디버거에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="80907-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80907-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80907-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="80907-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="80907-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80907-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80907-115">Requirements</span></span>  
 <span data-ttu-id="80907-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80907-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80907-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80907-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80907-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80907-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80907-119">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80907-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80907-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80907-120">See Also</span></span>  
 [<span data-ttu-id="80907-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80907-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="80907-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="80907-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
