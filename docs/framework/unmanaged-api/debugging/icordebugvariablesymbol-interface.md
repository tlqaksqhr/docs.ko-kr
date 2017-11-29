---
title: "ICorDebugVariableSymbol 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 89bae73e9dfb729e26f54dc7874418163870dc27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="1970c-102">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1970c-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="1970c-103">변수에 대한 디버그 기호 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1970c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-104">Methods</span></span>  
  
|<span data-ttu-id="1970c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-105">Method</span></span>|<span data-ttu-id="1970c-106">설명</span><span class="sxs-lookup"><span data-stu-id="1970c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1970c-107">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="1970c-108">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="1970c-109">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="1970c-110">변수의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="1970c-111">GetSlotIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="1970c-112">지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="1970c-113">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="1970c-114">변수의 값을 바이트 배열로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="1970c-115">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="1970c-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="1970c-116">바이트 배열의 값을 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1970c-117">설명</span><span class="sxs-lookup"><span data-stu-id="1970c-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1970c-118">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="1970c-119">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1970c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1970c-120">Requirements</span></span>  
 <span data-ttu-id="1970c-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1970c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1970c-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1970c-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1970c-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1970c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1970c-124">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1970c-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1970c-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1970c-125">See Also</span></span>  
 [<span data-ttu-id="1970c-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1970c-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1970c-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="1970c-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
