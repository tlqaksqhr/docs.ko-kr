---
title: "ICorDebugCode::GetVersionNumber 메서드"
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
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6efcfa60a6254081ea28aeb9d51f41410ab5049e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="bac8c-102">ICorDebugCode::GetVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="bac8c-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="bac8c-103">이 "ICorDebugCode"를 나타내는 코드의 버전을 식별 하는 1부터 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bac8c-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="bac8c-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bac8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bac8c-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="bac8c-106">[out] 코드의 버전 번호에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bac8c-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bac8c-107">설명</span><span class="sxs-lookup"><span data-stu-id="bac8c-107">Remarks</span></span>  
 <span data-ttu-id="bac8c-108">버전 번호는 코드에 편집 하며 계속 하기 (EnC) 연산이 수행 될 때마다 증가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac8c-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac8c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bac8c-109">Requirements</span></span>  
 <span data-ttu-id="bac8c-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bac8c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac8c-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bac8c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bac8c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bac8c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bac8c-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac8c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bac8c-114">See Also</span></span>  
 
