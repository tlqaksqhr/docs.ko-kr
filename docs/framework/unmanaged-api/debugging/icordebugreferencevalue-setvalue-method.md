---
title: "ICorDebugReferenceValue::SetValue 메서드"
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
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71250155d0c71b9b8f9cddad57d0c74b4ffc7991
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="a7ec7-102">ICorDebugReferenceValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a7ec7-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="a7ec7-103">지정된 된 메모리 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ec7-103">Sets the specified memory address.</span></span> <span data-ttu-id="a7ec7-104">즉,이 메서드는이 ICorDebugReferenceValue 개체를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ec7-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ec7-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7ec7-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7ec7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7ec7-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="a7ec7-107">[in] A `CORDB_ADDRESS` 이 개체의 주소를 지정 하는 값 `ICorDebugReferenceValue` 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ec7-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ec7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7ec7-108">Requirements</span></span>  
 <span data-ttu-id="a7ec7-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ec7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ec7-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7ec7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7ec7-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ec7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7ec7-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ec7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
