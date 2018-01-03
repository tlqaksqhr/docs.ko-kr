---
title: "ICorDebugFunction2::GetVersionNumber 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16902d1a50f691ae555fdbc964bb9a1c6bf563c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="3f0b6-102">ICorDebugFunction2::GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="3f0b6-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="3f0b6-103">이 함수의 편집 하며 계속 하기 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f0b6-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f0b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f0b6-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="3f0b6-106">[out] 이 ICorDebugFunction2 개체로 표시 되는 함수의 버전 번호는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f0b6-107">설명</span><span class="sxs-lookup"><span data-stu-id="3f0b6-107">Remarks</span></span>  
 <span data-ttu-id="3f0b6-108">런타임에서 수행 된 각 모듈에 디버그 세션 중 편집 수를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="3f0b6-109">하나는 함수의 버전 번호는 함수에 적용 된 편집의 수를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="3f0b6-110">함수의 원래 버전은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-110">The function's original version is version 1.</span></span> <span data-ttu-id="3f0b6-111">숫자는 모듈에 대 한 될 때마다 증가 [icordebugmodule2:: Applychanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) 해당 모듈에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="3f0b6-112">따라서 첫 번째 및 세 번째 호출에서 함수 본문이 바뀌었으면 `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` 버전 1, 2, 또는 해당 함수에 대해 4 하지만 하지 버전 3 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="3f0b6-113">(해당 함수 버전이 3 없는 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="3f0b6-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="3f0b6-114">버전 번호는 각 모듈에 대해 개별적으로 추적 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="3f0b6-115">따라서 모듈 1 및 모듈 2 없음에 4 개의 편집 작업을 수행 하는 경우 다음 편집 모듈 1에는 모듈 1의 모든 편집 된 함수에 6의 버전 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="3f0b6-116">모듈 2를 편집 하는 동일한 모듈 2에 포함 된 함수 2의 버전 번호를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="3f0b6-117">하 여 가져온 버전 번호는 `GetVersionNumber` 메서드를 여 가져온 보다 낮을 수도 [icordebugfunction:: Getcurrentversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="3f0b6-118">[icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) 메서드가 동일한 작업을 수행할 `ICorDebugFunction2::GetVersionNumber`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0b6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f0b6-119">Requirements</span></span>  
 <span data-ttu-id="3f0b6-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f0b6-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f0b6-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f0b6-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f0b6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f0b6-123">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0b6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
