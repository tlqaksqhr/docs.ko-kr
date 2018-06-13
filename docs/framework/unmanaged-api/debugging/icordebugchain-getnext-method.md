---
title: ICorDebugChain::GetNext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839052b72d908e48a4b6f88dab05ec3c3d575d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405413"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="78feb-102">ICorDebugChain::GetNext 메서드</span><span class="sxs-lookup"><span data-stu-id="78feb-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="78feb-103">스레드 프레임의 다음 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78feb-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78feb-104">구문</span><span class="sxs-lookup"><span data-stu-id="78feb-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78feb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78feb-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="78feb-106">[out] 스레드 프레임의 다음 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78feb-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="78feb-107">이 체인은 마지막 체인 경우 `ppChain` null입니다.</span><span class="sxs-lookup"><span data-stu-id="78feb-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78feb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78feb-108">Requirements</span></span>  
 <span data-ttu-id="78feb-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78feb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78feb-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78feb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78feb-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78feb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78feb-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78feb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
