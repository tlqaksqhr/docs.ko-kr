---
title: "ICorDebugBlockingObjectEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c05420a54d7a79198e235a39e578bedf296b4fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="1f092-102">ICorDebugBlockingObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="1f092-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="1f092-103">지정된 된 수의 가져옵니다 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 개체에서 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f092-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f092-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingOjbect values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f092-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f092-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1f092-106">[in] 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="1f092-107">[out] 에 대 한 포인터의 배열 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1f092-108">[out] 검색 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f092-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f092-109">Return Value</span></span>  
 <span data-ttu-id="1f092-110">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="1f092-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f092-111">HRESULT</span></span>|<span data-ttu-id="1f092-112">설명</span><span class="sxs-lookup"><span data-stu-id="1f092-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f092-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f092-113">S_OK</span></span>|<span data-ttu-id="1f092-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1f092-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1f092-115">S_FALSE</span></span>|<span data-ttu-id="1f092-116">`pceltFetched`이 `celt`와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f092-117">설명</span><span class="sxs-lookup"><span data-stu-id="1f092-117">Remarks</span></span>  
 <span data-ttu-id="1f092-118">이 메서드가 함수 같은 일반적인 COM 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="1f092-119">입력된 배열 값 이상 이어야 합니다 크기의 `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="1f092-120">배열을 채우는 사용 하 여 다음 `celt` 값을 열거형에 남아 있는 모든 값 보다 적으면 `celt` 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="1f092-121">이 메서드가 반환 될 때 `pceltFetched` 검색 된 값의 수로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="1f092-122">경우 `values` 잘못 된 포인터를 포함 하거나 보다 작은 버퍼를 가리키는 `celt`, if 또는 `pceltFetched` 잘못 된 포인터는 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f092-123">하지만 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) "ICorDebugValue" 인터페이스 내부에서 해제 되어야 하나요, 구조 해제 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="1f092-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f092-124">Requirements</span></span>  
 <span data-ttu-id="1f092-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f092-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f092-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f092-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f092-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f092-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f092-128">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f092-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f092-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f092-129">See Also</span></span>  
 [<span data-ttu-id="1f092-130">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f092-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="1f092-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f092-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1f092-132">디버깅</span><span class="sxs-lookup"><span data-stu-id="1f092-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
