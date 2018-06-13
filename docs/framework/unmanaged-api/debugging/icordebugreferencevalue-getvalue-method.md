---
title: ICorDebugReferenceValue::GetValue 메서드
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92df7bbcc2c391dd28f4075a97595762403d8def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416317"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="ddbf1-102">ICorDebugReferenceValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="ddbf1-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="ddbf1-103">참조 된 개체의 현재 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="ddbf1-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddbf1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ddbf1-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="ddbf1-106">[out] 에 대 한 포인터는 `CORDB_ADDRESS` 이 ICorDebugReferenceValue 개체가 가리키는 개체의 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddbf1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ddbf1-107">Requirements</span></span>  
 <span data-ttu-id="ddbf1-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddbf1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddbf1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddbf1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddbf1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddbf1-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddbf1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
