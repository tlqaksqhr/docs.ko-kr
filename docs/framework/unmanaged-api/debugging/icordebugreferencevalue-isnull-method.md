---
title: "ICorDebugReferenceValue::IsNull 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.IsNull
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53eaa411dc405142461de99bc787eba7a5d52db6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="6a395-102">ICorDebugReferenceValue::IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="6a395-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="6a395-103">이 ICorDebugReferenceValue이 null 값이 경우 인지 여부를 나타내는 값을 가져옵니다는 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a395-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a395-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a395-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a395-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a395-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="6a395-106">[out] 부울 값이에 대 한 포인터 `true` 이 `ICorDebugReferenceValue` 개체는 null이 고, 그렇지 않으면 `pbNull` 은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6a395-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a395-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a395-107">Requirements</span></span>  
 <span data-ttu-id="6a395-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a395-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a395-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a395-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a395-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a395-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a395-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a395-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
