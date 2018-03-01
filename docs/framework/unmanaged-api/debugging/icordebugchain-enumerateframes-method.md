---
title: "ICorDebugChain::EnumerateFrames 메서드"
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
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="c073e-102">ICorDebugChain::EnumerateFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="c073e-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="c073e-103">가장 최근의 프레임부터 체인에 있는 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c073e-104">구문</span><span class="sxs-lookup"><span data-stu-id="c073e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c073e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c073e-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="c073e-106">[out] 스택 프레임에 대 한 열거자를 ICorDebugFrameEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c073e-107">설명</span><span class="sxs-lookup"><span data-stu-id="c073e-107">Remarks</span></span>  
 <span data-ttu-id="c073e-108">체인의 스레드에 대 한 실제 호출 스택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="c073e-109">`EnumerateFrames` 관리 되는 체인에 대 한 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="c073e-110">디버깅 API는 관리 되지 않는 체인에 포함 된 프레임을 가져오기 위한 메서드를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="c073e-111">디버거는이 정보를 가져오는 다른 방법을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c073e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c073e-112">Requirements</span></span>  
 <span data-ttu-id="c073e-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c073e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c073e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c073e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c073e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c073e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c073e-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c073e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
