---
title: "ICorDebugChain::GetActiveFrame 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7498e031b74bd904b908342b663e4421432e6d95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="714ff-102">ICorDebugChain::GetActiveFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="714ff-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="714ff-103">활성 가져옵니다 (즉, 가장 최근의) 프레임 체인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="714ff-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="714ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="714ff-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="714ff-106">[out] 활성 나타내는 ICorDebugFrame 개체의 주소에 대 한 포인터 (즉, 가장 최근의) 프레임 체인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="714ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="714ff-107">Remarks</span></span>  
 <span data-ttu-id="714ff-108">관리 되는 스택 프레임이 사용할 수 있는 경우 `ppFrame` 설정 되어 null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="714ff-109">활성 프레임을 사용할 수 없는 경우에 호출이 성공 하 고 `ppFrame` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="714ff-110">활성 프레임 CHAIN_ENTER_UNMANAGED, 인해 시작 체인에 대해 및 CHAIN_CLASS_INIT 인해 시작 된 일부 체인에 대해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="714ff-111">CorDebugChainReason 열거형을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="714ff-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714ff-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="714ff-112">Requirements</span></span>  
 <span data-ttu-id="714ff-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="714ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714ff-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="714ff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="714ff-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="714ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="714ff-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
