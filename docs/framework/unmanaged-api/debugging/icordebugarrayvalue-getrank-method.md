---
title: "ICorDebugArrayValue::GetRank 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetRank
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b821e23b9b45932fb9296e0d4dac81d2b8c06135
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="7be0f-102">ICorDebugArrayValue::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="7be0f-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="7be0f-103">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7be0f-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7be0f-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7be0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7be0f-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="7be0f-106">[out] 이 차원 수에 대 한 포인터 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7be0f-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be0f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7be0f-107">Requirements</span></span>  
 <span data-ttu-id="7be0f-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7be0f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be0f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7be0f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7be0f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be0f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be0f-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be0f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
