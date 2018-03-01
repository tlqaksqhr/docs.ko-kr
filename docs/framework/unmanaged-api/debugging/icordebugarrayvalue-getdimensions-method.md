---
title: "ICorDebugArrayValue::GetDimensions 메서드"
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
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1769969d411d66417d2b2df7ddc9f810bd7f48ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="fae78-102">ICorDebugArrayValue::GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="fae78-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="fae78-103">이 배열의 각 차원에 있는 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fae78-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae78-104">구문</span><span class="sxs-lookup"><span data-stu-id="fae78-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fae78-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fae78-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="fae78-106">[in] 차원이 ICorDebugArrayValue 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fae78-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="fae78-107">또한이 값은의 크기는 `dims` 배열 크기의 차원 수와 같은지는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fae78-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="fae78-108">[out] 이 차원에 있는 요소 수를 지정는 각각 정수, 배열 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fae78-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fae78-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fae78-109">Requirements</span></span>  
 <span data-ttu-id="fae78-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fae78-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae78-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fae78-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fae78-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fae78-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fae78-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae78-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
