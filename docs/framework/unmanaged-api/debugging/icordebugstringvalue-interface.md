---
title: ICorDebugStringValue Interface1
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
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9958e6f5ad73658b278d83c78e58cf4166d5642
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstringvalue-interface1"></a><span data-ttu-id="cc421-102">ICorDebugStringValue Interface1</span><span class="sxs-lookup"><span data-stu-id="cc421-102">ICorDebugStringValue Interface1</span></span>
<span data-ttu-id="cc421-103">문자열 값에 적용 되는 ICorDebugHeapValue의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cc421-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc421-104">메서드</span><span class="sxs-lookup"><span data-stu-id="cc421-104">Methods</span></span>  
  
|<span data-ttu-id="cc421-105">메서드</span><span class="sxs-lookup"><span data-stu-id="cc421-105">Method</span></span>|<span data-ttu-id="cc421-106">설명</span><span class="sxs-lookup"><span data-stu-id="cc421-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc421-107">GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="cc421-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="cc421-108">이 참조 하는 문자열의 문자 수를 가져옵니다 `ICorDebugStringValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc421-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="cc421-109">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="cc421-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="cc421-110">이 참조 하는 문자열을 가져옵니다 `ICorDebugStringValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc421-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc421-111">설명</span><span class="sxs-lookup"><span data-stu-id="cc421-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc421-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc421-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc421-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc421-113">Requirements</span></span>  
 <span data-ttu-id="cc421-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cc421-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc421-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc421-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc421-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc421-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc421-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc421-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc421-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc421-118">See Also</span></span>  
 [<span data-ttu-id="cc421-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc421-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
