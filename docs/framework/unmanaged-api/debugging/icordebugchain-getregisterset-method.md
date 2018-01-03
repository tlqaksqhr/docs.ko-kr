---
title: "ICorDebugChain::GetRegisterSet 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2463c0860591a9642ac52a333b7540549d7e9183
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="ed9c0-102">ICorDebugChain::GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="ed9c0-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="ed9c0-103">레지스터를이 체인의 활성 부분에 대 한 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed9c0-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed9c0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed9c0-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="ed9c0-106">[out] 주소에 대 한 포인터는 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 이 체인의 활성 부분에 대 한 설정의 레지스터를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed9c0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed9c0-107">Requirements</span></span>  
 <span data-ttu-id="ed9c0-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed9c0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed9c0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed9c0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed9c0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed9c0-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed9c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
