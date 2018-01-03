---
title: "ICorDebugHeapValue::IsValid 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue.IsValid
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f4f356c953feaf0e6597983f431222a469e90c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="22264-102">ICorDebugHeapValue::IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="22264-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="22264-103">이 ICorDebugHeapValue가 나타내는 개체가 유효한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22264-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="22264-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="22264-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22264-105">구문</span><span class="sxs-lookup"><span data-stu-id="22264-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22264-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22264-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="22264-107">[out] 힙에서이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="22264-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22264-108">설명</span><span class="sxs-lookup"><span data-stu-id="22264-108">Remarks</span></span>  
 <span data-ttu-id="22264-109">값은 가비지 수집기에서 회수 된 경우에 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22264-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="22264-110">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22264-110">This method has been deprecated.</span></span> <span data-ttu-id="22264-111">.NET Framework 2.0에서 모든 값은 유효 기간 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 될 때 값은 유효성을 검사 하지 않습니다.에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22264-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22264-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22264-112">Requirements</span></span>  
 <span data-ttu-id="22264-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22264-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22264-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22264-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22264-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22264-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22264-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22264-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
