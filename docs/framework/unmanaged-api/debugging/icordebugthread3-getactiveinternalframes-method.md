---
title: "ICorDebugThread3::GetActiveInternalFrames 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ecfbaeff9416ee8e6541a23bac6ec76f99abd2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="a1211-102">ICorDebugThread3::GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="a1211-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="a1211-103">내부 프레임의 배열을 반환 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체)를 스택에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1211-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1211-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1211-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1211-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="a1211-106">[in] 예상 하는 내부 프레임 수가 `ppInternalFrames`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="a1211-107">[out] 에 대 한 포인터는 `ULONG32` 내부 스택 프레임의 수가 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="a1211-108">[out에서] 내부 스택 프레임의 배열의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1211-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a1211-109">Return Value</span></span>  
 <span data-ttu-id="a1211-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a1211-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1211-111">HRESULT</span></span>|<span data-ttu-id="a1211-112">설명</span><span class="sxs-lookup"><span data-stu-id="a1211-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1211-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1211-113">S_OK</span></span>|<span data-ttu-id="a1211-114">[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체가 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="a1211-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a1211-115">E_INVALIDARG</span></span>|<span data-ttu-id="a1211-116">`cInternalFrames`0이 아닌 및 `ppInternalFrames` 은 `null`, 또는 `pcInternalFrames` 은 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="a1211-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="a1211-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="a1211-118">`ppInternalFrames`내부 프레임의 개수 보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a1211-119">예외</span><span class="sxs-lookup"><span data-stu-id="a1211-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1211-120">설명</span><span class="sxs-lookup"><span data-stu-id="a1211-120">Remarks</span></span>  
 <span data-ttu-id="a1211-121">내부 프레임은 임시 데이터를 저장 하려면 런타임에 의해 스택에 밀어 넣은 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="a1211-122">처음 호출할 때는 `GetActiveInternalFrames`를 설정 해야는 `cInternalFrames` 매개 변수를 0 (영) 및 `ppInternalFrames` 매개 변수를 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="a1211-123">때 `GetActiveInternalFrames` 먼저 반환 `pcInternalFrames` 스택에 내부 프레임 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="a1211-124">`GetActiveInternalFrames`다음 해야를 두 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="a1211-125">적절 한 수를 전달 해야 (`pcInternalFrames`)에 `cInternalFrames` 매개 변수를 적절 한 크기의 배열에 대 한 포인터를 지정 하 고 `ppInternalFrames`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="a1211-126">사용 하 여는 [icordebugstackwalk:: Getframe](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) 실제 반환 하는 메서드 스택 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1211-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1211-127">Requirements</span></span>  
 <span data-ttu-id="a1211-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1211-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1211-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1211-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1211-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1211-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1211-131">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1211-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1211-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1211-132">See Also</span></span>  
 [<span data-ttu-id="a1211-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1211-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a1211-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="a1211-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
