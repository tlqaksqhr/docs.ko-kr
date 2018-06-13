---
title: ICorDebugChain::GetPrevious 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c0545440ed63ba914229249080ec9f6be8eb2b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402255"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="66df8-102">ICorDebugChain::GetPrevious 메서드</span><span class="sxs-lookup"><span data-stu-id="66df8-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="66df8-103">스레드에 대 한 이전 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66df8-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66df8-104">구문</span><span class="sxs-lookup"><span data-stu-id="66df8-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66df8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66df8-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="66df8-106">[out] 이 스레드에 대 한 프레임의 이전 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66df8-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="66df8-107">이 체인은 첫 번째 체인 경우 `ppChain` null입니다.</span><span class="sxs-lookup"><span data-stu-id="66df8-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66df8-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66df8-108">Requirements</span></span>  
 <span data-ttu-id="66df8-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66df8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66df8-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66df8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66df8-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66df8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66df8-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66df8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
