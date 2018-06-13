---
title: ICorDebugGenericValue::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6d30a9f03d8717486be7cd89bb182d350a82df7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411638"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="a736d-102">ICorDebugGenericValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a736d-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="a736d-103">지정된 된 버퍼에이 제네릭의 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a736d-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a736d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a736d-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a736d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a736d-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="a736d-106">[out] 이 ICorDebugGenericValue 개체로 표시 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a736d-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="a736d-107">값은 단순 형식 또는 참조 형식 (즉, 포인터) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a736d-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a736d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a736d-108">Requirements</span></span>  
 <span data-ttu-id="a736d-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a736d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a736d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a736d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a736d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a736d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a736d-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a736d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
