---
title: "ICorDebugMemoryBuffer 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80002d064c48a90236a64a3d0a56fab5877cf411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="d1534-102">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1534-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="d1534-103">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1534-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d1534-104">Methods</span></span>  
  
|<span data-ttu-id="d1534-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d1534-105">Method</span></span>|<span data-ttu-id="d1534-106">설명</span><span class="sxs-lookup"><span data-stu-id="d1534-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1534-107">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="d1534-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="d1534-108">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="d1534-109">GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="d1534-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="d1534-110">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1534-111">설명</span><span class="sxs-lookup"><span data-stu-id="d1534-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1534-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d1534-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1534-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1534-114">Requirements</span></span>  
 <span data-ttu-id="d1534-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1534-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1534-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1534-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1534-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1534-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1534-118">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1534-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1534-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1534-119">See Also</span></span>  
 [<span data-ttu-id="d1534-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1534-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d1534-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="d1534-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
