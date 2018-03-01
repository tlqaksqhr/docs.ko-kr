---
title: "ICorDebugObjectValue::GetClass 메서드"
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
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6135dd3806d72b59ce858fab9d0a0b6c3b1f11b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="4b724-102">ICorDebugObjectValue::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="4b724-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="4b724-103">이 개체 값의 클래스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b724-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b724-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b724-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b724-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b724-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="4b724-106">[out] 개체 값이 "ICorDebugObjectValue" 개체가 나타내는 클래스를 나타내는 "ICorDebugClass" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4b724-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b724-107">설명</span><span class="sxs-lookup"><span data-stu-id="4b724-107">Remarks</span></span>  
 <span data-ttu-id="4b724-108">`GetClass` 및 [icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 하며 둘 다로 대체 되기 제네릭 인식 [icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b724-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b724-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b724-109">Requirements</span></span>  
 <span data-ttu-id="4b724-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b724-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b724-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b724-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b724-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b724-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b724-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b724-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b724-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b724-114">See Also</span></span>  
    
 
