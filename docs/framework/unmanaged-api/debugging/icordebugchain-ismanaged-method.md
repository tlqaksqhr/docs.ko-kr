---
title: ICorDebugChain::IsManaged 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c61cc12e438c0786b6e093b8bb1ea288a42e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401169"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="0b7bc-102">ICorDebugChain::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="0b7bc-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="0b7bc-103">이 체인 관리 되는 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b7bc-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b7bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b7bc-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b7bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b7bc-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="0b7bc-106">[out] `true` 이 체인 관리 되는 코드를 실행 하는 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7bc-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b7bc-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b7bc-107">Requirements</span></span>  
 <span data-ttu-id="0b7bc-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7bc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b7bc-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b7bc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b7bc-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b7bc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b7bc-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b7bc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
