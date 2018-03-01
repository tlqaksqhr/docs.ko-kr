---
title: "ICorDebugReferenceValue::GetValue 메서드"
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
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d7be70ec41b2044b4af10e102218ce487e4a5e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="1d8cc-102">ICorDebugReferenceValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="1d8cc-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="1d8cc-103">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d8cc-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d8cc-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d8cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d8cc-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="1d8cc-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 ICorDebugReferenceValue 개체가 가리키는 개체의 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d8cc-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d8cc-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d8cc-107">Requirements</span></span>  
 <span data-ttu-id="1d8cc-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d8cc-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d8cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d8cc-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d8cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d8cc-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d8cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
