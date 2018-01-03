---
title: "ICorDebugEval::IsActive 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b574d74de1e042ab50e52eb3bb2fe217801bf1eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="5c1a3-102">ICorDebugEval::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="5c1a3-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="5c1a3-103">ICorDebugEval 개체가이 현재 실행 되 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a3-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c1a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c1a3-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c1a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c1a3-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="5c1a3-106">[out] 이 평가 활성 상태 인지 여부를 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a3-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c1a3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c1a3-107">Requirements</span></span>  
 <span data-ttu-id="5c1a3-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c1a3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c1a3-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c1a3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c1a3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c1a3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c1a3-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c1a3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
