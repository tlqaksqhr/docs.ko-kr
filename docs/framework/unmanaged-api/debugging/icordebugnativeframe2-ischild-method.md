---
title: "ICorDebugNativeFrame2::IsChild 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.IsChild Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 006543e473ca3b7cc1818b2b4641567ce37f6f0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="12cd4-102">ICorDebugNativeFrame2::IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="12cd4-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="12cd4-103">현재 프레임이 자식 프레임이 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12cd4-104">구문</span><span class="sxs-lookup"><span data-stu-id="12cd4-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12cd4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12cd4-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="12cd4-106">[out] 현재 프레임이 자식 프레임이 되는지를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12cd4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="12cd4-107">Return Value</span></span>  
 <span data-ttu-id="12cd4-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="12cd4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12cd4-109">HRESULT</span></span>|<span data-ttu-id="12cd4-110">설명</span><span class="sxs-lookup"><span data-stu-id="12cd4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12cd4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="12cd4-111">S_OK</span></span>|<span data-ttu-id="12cd4-112">자식 상태가 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="12cd4-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12cd4-113">E_FAIL</span></span>|<span data-ttu-id="12cd4-114">자식 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="12cd4-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="12cd4-115">E_INVALIDARG</span></span>|<span data-ttu-id="12cd4-116">`pIsChild`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="12cd4-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="12cd4-117">예외</span><span class="sxs-lookup"><span data-stu-id="12cd4-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12cd4-118">설명</span><span class="sxs-lookup"><span data-stu-id="12cd4-118">Remarks</span></span>  
 <span data-ttu-id="12cd4-119">`IsChild` 메서드 반환 `true` 프레임 개체 메서드를 호출 하는 다른 프레임의 자식인 경우.</span><span class="sxs-lookup"><span data-stu-id="12cd4-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="12cd4-120">이 경우 사용 하 여는 [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) 메서드 프레임 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12cd4-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12cd4-121">Requirements</span></span>  
 <span data-ttu-id="12cd4-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12cd4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12cd4-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12cd4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12cd4-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12cd4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12cd4-125">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12cd4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cd4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12cd4-126">See Also</span></span>  
 [<span data-ttu-id="12cd4-127">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12cd4-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="12cd4-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12cd4-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="12cd4-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="12cd4-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
