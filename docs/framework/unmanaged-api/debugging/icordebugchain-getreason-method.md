---
title: ICorDebugChain::GetReason 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d02a68e80e34be906e9fe09f3457a0f2214c6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405069"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="1e054-102">ICorDebugChain::GetReason 메서드</span><span class="sxs-lookup"><span data-stu-id="1e054-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="1e054-103">이 호출 체인이 발생 한 이유를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e054-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e054-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e054-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e054-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="1e054-106">[out] 이 호출 체인이 발생 한 이유를 나타내는 CorDebugChainReason 열거형의 값 (비트 조합)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e054-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e054-107">Requirements</span></span>  
 <span data-ttu-id="1e054-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e054-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e054-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e054-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e054-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e054-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e054-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e054-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
