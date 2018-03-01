---
title: "ICorDebugChain::GetReason 메서드"
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
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c23385c0d7b6173659e071735dee5d2d75a9e33a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="e49ae-102">ICorDebugChain::GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="e49ae-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="e49ae-103">이 호출 체인이 발생 한 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e49ae-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="e49ae-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e49ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e49ae-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="e49ae-106">[out] 이 호출 체인이 발생 한 이유를 나타내는 CorDebugChainReason 열거형의 값 (비트 조합)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e49ae-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49ae-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e49ae-107">Requirements</span></span>  
 <span data-ttu-id="e49ae-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e49ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49ae-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e49ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e49ae-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e49ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e49ae-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
