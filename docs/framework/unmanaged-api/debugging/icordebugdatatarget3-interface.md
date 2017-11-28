---
title: "ICorDebugDataTarget3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1ab94e792265916e29ed24239e25cb5d57d1313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="b44cf-102">ICorDebugDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b44cf-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="b44cf-103">논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b44cf-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="b44cf-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b44cf-104">Method</span></span>  
  
|<span data-ttu-id="b44cf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b44cf-105">Method</span></span>|<span data-ttu-id="b44cf-106">설명</span><span class="sxs-lookup"><span data-stu-id="b44cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b44cf-107">GetLoadedModules 메서드</span><span class="sxs-lookup"><span data-stu-id="b44cf-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="b44cf-108">지금까지 로드된 모듈 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b44cf-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b44cf-109">설명</span><span class="sxs-lookup"><span data-stu-id="b44cf-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b44cf-110">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44cf-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b44cf-111">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="b44cf-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b44cf-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b44cf-112">Requirements</span></span>  
 <span data-ttu-id="b44cf-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b44cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b44cf-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b44cf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b44cf-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b44cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b44cf-116">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b44cf-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b44cf-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b44cf-117">See Also</span></span>  
 [<span data-ttu-id="b44cf-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b44cf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b44cf-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="b44cf-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
