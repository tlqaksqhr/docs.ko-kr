---
title: "ICorDebugVariableHomeEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum
helpviewer_keywords: ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e64a52ca70606f83138b636f7ccb62ba18908f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="52b9f-102">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52b9f-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="52b9f-103">지역 변수 및 함수에 인수에는 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b9f-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52b9f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="52b9f-104">Methods</span></span>  
  
|<span data-ttu-id="52b9f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="52b9f-105">Method</span></span>|<span data-ttu-id="52b9f-106">설명</span><span class="sxs-lookup"><span data-stu-id="52b9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52b9f-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="52b9f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="52b9f-108">지정된 된 수의 가져옵니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 로컬 변수 및 인수는 함수에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="52b9f-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52b9f-109">설명</span><span class="sxs-lookup"><span data-stu-id="52b9f-109">Remarks</span></span>  
 <span data-ttu-id="52b9f-110">`ICorDebugVariableHomeEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="52b9f-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="52b9f-111">`ICorDebugVariableHomeEnum` 인스턴스 채워집니다 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 호출 하 여 인스턴스는 [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="52b9f-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="52b9f-112">각 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 인스턴스 컬렉션에 있는 지역 변수 또는 함수에 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52b9f-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="52b9f-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 호출 하 여 컬렉션의 개체를 열거할 수는 [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="52b9f-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52b9f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52b9f-114">Requirements</span></span>  
 <span data-ttu-id="52b9f-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52b9f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52b9f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52b9f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52b9f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52b9f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52b9f-118">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52b9f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b9f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52b9f-119">See Also</span></span>  
 [<span data-ttu-id="52b9f-120">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52b9f-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="52b9f-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52b9f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
