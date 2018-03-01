---
title: "ICorDebugValue::GetType 메서드"
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
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a79ef332361fdaa3a23cc4e13daa8b4a8303d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="013cd-102">ICorDebugValue::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="013cd-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="013cd-103">이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="013cd-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="013cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="013cd-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="013cd-106">[out] 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="013cd-107">설명</span><span class="sxs-lookup"><span data-stu-id="013cd-107">Remarks</span></span>  
 <span data-ttu-id="013cd-108">개체가 복잡 한 런타임 형식이의 적절 한 하위 클래스를 통해 해당 형식을 검사할 수 있습니다는 `ICorDebugValue` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="013cd-109">예를 들어 "ICorDebugObjectValue"에서 상속 하는 `ICorDebugValue`, 복합 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="013cd-110">`GetType` 및 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="013cd-111">둘 다로 대체 되기 제네릭 인식 [icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="013cd-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="013cd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="013cd-112">Requirements</span></span>  
 <span data-ttu-id="013cd-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="013cd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="013cd-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="013cd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="013cd-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="013cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="013cd-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="013cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013cd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="013cd-117">See Also</span></span>  
 
