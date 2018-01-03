---
title: "ICorDebugHeapEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9869542b04b26fdf343b4112c2f84a26a3061c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="9b32f-102">ICorDebugHeapEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="9b32f-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="9b32f-103">지정된 된 수의 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9b32f-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b32f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b32f-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b32f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b32f-105">Parameters</span></span>  
 <span data-ttu-id="9b32f-106">celt</span><span class="sxs-lookup"><span data-stu-id="9b32f-106">celt</span></span>  
 <span data-ttu-id="9b32f-107">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="9b32f-108">개체</span><span class="sxs-lookup"><span data-stu-id="9b32f-108">objects</span></span>  
 <span data-ttu-id="9b32f-109">[out] 각각 가리키는 포인터의 배열은 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="9b32f-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9b32f-110">pceltFetched</span></span>  
 <span data-ttu-id="9b32f-111">[out] 수에 대 한 포인터 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 에 실제로 반환 된 개체 `objects`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="9b32f-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b32f-113">설명</span><span class="sxs-lookup"><span data-stu-id="9b32f-113">Remarks</span></span>  
 <span data-ttu-id="9b32f-114">`COR_HEAPOBJECT.type` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="9b32f-115">이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b32f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b32f-116">Requirements</span></span>  
 <span data-ttu-id="9b32f-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b32f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b32f-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b32f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b32f-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b32f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b32f-120">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b32f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b32f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b32f-121">See Also</span></span>  
 [<span data-ttu-id="9b32f-122">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b32f-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 [<span data-ttu-id="9b32f-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b32f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
