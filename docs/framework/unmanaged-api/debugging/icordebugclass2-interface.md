---
title: ICorDebugClass2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2
helpviewer_keywords: ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c4f96f084a96ccdc9857a64217284b485aa73a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="6e485-102">ICorDebugClass2 Interface1</span><span class="sxs-lookup"><span data-stu-id="6e485-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="6e485-103">제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="6e485-104">이 인터페이스를 확장 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e485-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6e485-105">Methods</span></span>  
  
|<span data-ttu-id="6e485-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6e485-106">Method</span></span>|<span data-ttu-id="6e485-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e485-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e485-108">GetParameterizedType 메서드</span><span class="sxs-lookup"><span data-stu-id="6e485-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="6e485-109">이 클래스에 대 한 형식 선언을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="6e485-110">SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="6e485-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="6e485-111">이 클래스의 각 메서드에 대해 메서드가 사용자 지정 코드 인지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e485-112">설명</span><span class="sxs-lookup"><span data-stu-id="6e485-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e485-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e485-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e485-114">Requirements</span></span>  
 <span data-ttu-id="6e485-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e485-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e485-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e485-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e485-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e485-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e485-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e485-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e485-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e485-119">See Also</span></span>  
 [<span data-ttu-id="6e485-120">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="6e485-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [<span data-ttu-id="6e485-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e485-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
