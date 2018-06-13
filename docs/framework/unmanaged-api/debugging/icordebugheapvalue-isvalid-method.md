---
title: ICorDebugHeapValue::IsValid 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95532d6721467b482b1d79d611f8055b606bb4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413510"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="96ea6-102">ICorDebugHeapValue::IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="96ea6-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="96ea6-103">이 ICorDebugHeapValue가 나타내는 개체가 유효한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="96ea6-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ea6-105">구문</span><span class="sxs-lookup"><span data-stu-id="96ea6-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96ea6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96ea6-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="96ea6-107">[out] 힙에서이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96ea6-108">설명</span><span class="sxs-lookup"><span data-stu-id="96ea6-108">Remarks</span></span>  
 <span data-ttu-id="96ea6-109">값은 가비지 수집기에서 회수 된 경우에 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="96ea6-110">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-110">This method has been deprecated.</span></span> <span data-ttu-id="96ea6-111">.NET Framework 2.0에서 모든 값은 유효 기간 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 될 때 값은 유효성을 검사 하지 않습니다.에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96ea6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96ea6-112">Requirements</span></span>  
 <span data-ttu-id="96ea6-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96ea6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96ea6-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96ea6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96ea6-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96ea6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96ea6-116">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ea6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
