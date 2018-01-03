---
title: "ICorDebugDataTarget2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2aefdb34277d2cb7ebc29ef817745b85064475d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="203d9-102">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="203d9-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="203d9-103">논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="203d9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-104">Methods</span></span>  
  
|<span data-ttu-id="203d9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-105">Method</span></span>|<span data-ttu-id="203d9-106">설명</span><span class="sxs-lookup"><span data-stu-id="203d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="203d9-107">CreateVirtualUnwinder 메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="203d9-108">초기 컨텍스트(반드시 스레드의 리프일 필요는 없음)에서 해제를 시작하는 새 스택 해제기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="203d9-109">EnumerateThreadIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="203d9-110">활성 스레드 ID의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="203d9-111">GetImageFromPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="203d9-112">모듈 기본 주소와 크기를 해당 모듈의 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="203d9-113">GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="203d9-114">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="203d9-115">GetSymbolProviderForImage 메서드</span><span class="sxs-lookup"><span data-stu-id="203d9-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="203d9-116">모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="203d9-117">설명</span><span class="sxs-lookup"><span data-stu-id="203d9-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="203d9-118">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="203d9-119">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="203d9-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="203d9-120">Requirements</span></span>  
 <span data-ttu-id="203d9-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="203d9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="203d9-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="203d9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="203d9-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="203d9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="203d9-124">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="203d9-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203d9-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="203d9-125">See Also</span></span>  
 [<span data-ttu-id="203d9-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="203d9-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="203d9-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="203d9-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
