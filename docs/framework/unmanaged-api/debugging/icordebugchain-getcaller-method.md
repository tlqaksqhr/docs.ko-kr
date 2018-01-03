---
title: "ICorDebugChain::GetCaller 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17c55358a1d502ce5946617556222282ac4c4fca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="e4c8c-102">ICorDebugChain::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="e4c8c-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="e4c8c-103">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e4c8c-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4c8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4c8c-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="e4c8c-106">[out] 호출 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="e4c8c-107">이 체인 이라고 자연스럽 게 (처럼의 경우가이 체인이 나 디버거가 호출 스택을 초기화 하는 경우), `ppChain` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4c8c-108">설명</span><span class="sxs-lookup"><span data-stu-id="e4c8c-108">Remarks</span></span>  
 <span data-ttu-id="e4c8c-109">호출 체인은 호출 스레드 간에 마샬링된 경우 다른 스레드에서 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c8c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4c8c-110">Requirements</span></span>  
 <span data-ttu-id="e4c8c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4c8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4c8c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4c8c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4c8c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4c8c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4c8c-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4c8c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
