---
title: "ICorDebugLoadedModule 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cc7a36deb7c81ccf67427b833dead7127619b39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="d179e-102">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d179e-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="d179e-103">로드된 모듈에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d179e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d179e-104">Methods</span></span>  
  
|<span data-ttu-id="d179e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d179e-105">Method</span></span>|<span data-ttu-id="d179e-106">설명</span><span class="sxs-lookup"><span data-stu-id="d179e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d179e-107">GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="d179e-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="d179e-108">로드된 모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="d179e-109">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="d179e-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="d179e-110">로드된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="d179e-111">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="d179e-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="d179e-112">로드된 모듈의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d179e-113">설명</span><span class="sxs-lookup"><span data-stu-id="d179e-113">Remarks</span></span>  
 <span data-ttu-id="d179e-114">`ICorDebugLoadedModule` 인터페이스는 디버거에서 구현되며 CLR 디버깅 인터페이스가 디버거에서 로드된 모듈에 대한 정보를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d179e-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d179e-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d179e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d179e-117">Requirements</span></span>  
 <span data-ttu-id="d179e-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d179e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d179e-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d179e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d179e-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d179e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d179e-121">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d179e-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d179e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d179e-122">See Also</span></span>  
 [<span data-ttu-id="d179e-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d179e-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d179e-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="d179e-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
