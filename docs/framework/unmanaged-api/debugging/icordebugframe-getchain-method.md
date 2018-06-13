---
title: ICorDebugFrame::GetChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c020b9f6c074be11e3433939ce6898586123cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412609"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="0fae6-102">ICorDebugFrame::GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="0fae6-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="0fae6-103">이 프레임의 일부인 체인에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0fae6-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fae6-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fae6-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fae6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0fae6-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="0fae6-106">[out] 이 프레임을 포함 하는 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0fae6-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fae6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0fae6-107">Requirements</span></span>  
 <span data-ttu-id="0fae6-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fae6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fae6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fae6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fae6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fae6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fae6-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fae6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
