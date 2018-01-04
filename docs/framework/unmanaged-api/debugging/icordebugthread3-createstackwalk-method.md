---
title: "ICorDebugThread3::CreateStackWalk 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.CreateStackWalk Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3b587a69c7acc3115c282eac065d304dc892b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="dbe09-102">ICorDebugThread3::CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="dbe09-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="dbe09-103">만듭니다는 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 해당 스택 해제 하려는 스레드에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe09-104">구문</span><span class="sxs-lookup"><span data-stu-id="dbe09-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbe09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dbe09-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="dbe09-106">[out] 주소에 대 한 포인터는 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 해당 스택 해제 하려는 스레드에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbe09-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="dbe09-107">Return Value</span></span>  
 <span data-ttu-id="dbe09-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dbe09-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbe09-109">HRESULT</span></span>|<span data-ttu-id="dbe09-110">설명</span><span class="sxs-lookup"><span data-stu-id="dbe09-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbe09-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbe09-111">S_OK</span></span>|<span data-ttu-id="dbe09-112">`ICorDebugStackWalk` 개체가 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="dbe09-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbe09-113">E_FAIL</span></span>|<span data-ttu-id="dbe09-114">`ICorDebugStackWalk` 개체가 만들어지지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="dbe09-115">예외</span><span class="sxs-lookup"><span data-stu-id="dbe09-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe09-116">설명</span><span class="sxs-lookup"><span data-stu-id="dbe09-116">Remarks</span></span>  
 <span data-ttu-id="dbe09-117">경우는 `CreateStackWalk` 메서드가 성공 하면 반환 된 `ICorDebugStackWalk` 개체의 컨텍스트는 스레드의 현재 컨텍스트로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe09-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbe09-118">Requirements</span></span>  
 <span data-ttu-id="dbe09-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe09-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe09-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbe09-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbe09-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe09-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe09-122">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe09-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe09-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbe09-123">See Also</span></span>  
 [<span data-ttu-id="dbe09-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dbe09-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dbe09-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="dbe09-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
