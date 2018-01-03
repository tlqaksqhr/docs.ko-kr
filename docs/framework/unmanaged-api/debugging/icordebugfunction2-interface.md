---
title: ICorDebugFunction2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2
helpviewer_keywords: ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac3a4cd5ec2aff1b60cd51ca33d411e5cc81eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="c2556-102">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="c2556-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="c2556-103">내 코드만 단계별 디버깅에 대 한 지원을 제공 하는 사용자 코드가 아닌 건너뜁니다 ICorDebugFunction 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2556-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-104">Methods</span></span>  
  
|<span data-ttu-id="c2556-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-105">Method</span></span>|<span data-ttu-id="c2556-106">설명</span><span class="sxs-lookup"><span data-stu-id="c2556-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2556-107">EnumerateNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="c2556-108">(아직 구현 되지 않았습니다.) 이 ICorDebugFunction2 개체에서 참조 하는 함수에서 네이티브 코드 문을 포함 하는 ICorDebugCodeEnum에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="c2556-109">GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="c2556-110">이 함수는 사용자 코드로 표시 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="c2556-111">GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="c2556-112">이 함수의 편집 하며 계속 하기 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="c2556-113">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="c2556-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="c2556-114">이 함수 내 코드만 표시를 단계별로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2556-115">설명</span><span class="sxs-lookup"><span data-stu-id="c2556-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2556-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2556-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2556-117">Requirements</span></span>  
 <span data-ttu-id="c2556-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2556-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2556-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2556-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2556-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2556-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2556-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2556-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2556-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2556-122">See Also</span></span>  
 [<span data-ttu-id="c2556-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2556-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
