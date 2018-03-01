---
title: "ICorDebugValue3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6a470113dc54876937850294f6d99fc15a2cf98e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="3046a-102">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3046a-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="3046a-103">2GB 보다 큰 배열에 대 한 지원을 제공 하는 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3046a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3046a-104">Methods</span></span>  
  
|<span data-ttu-id="3046a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3046a-105">Method</span></span>|<span data-ttu-id="3046a-106">설명</span><span class="sxs-lookup"><span data-stu-id="3046a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3046a-107">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="3046a-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="3046a-108">이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue3` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3046a-109">설명</span><span class="sxs-lookup"><span data-stu-id="3046a-109">Remarks</span></span>  
 <span data-ttu-id="3046a-110">[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 0에서 2147483647 바이트를 하는 개체 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="3046a-111">에 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 배열의 크기는 2GB를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="3046a-112">`ICorDebugValue3` 인터페이스를 사용 하면 이러한 배열 크기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3046a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3046a-113">Requirements</span></span>  
 <span data-ttu-id="3046a-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3046a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3046a-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3046a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3046a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3046a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3046a-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3046a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3046a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3046a-118">See Also</span></span>  
    
    
 [<span data-ttu-id="3046a-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3046a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3046a-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="3046a-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
