---
title: "ICorDebugAppDomain::EnumerateSteppers 메서드"
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
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b410eabee546307488449e577d9e102ac6a210b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="6be31-102">ICorDebugAppDomain::EnumerateSteppers 메서드</span><span class="sxs-lookup"><span data-stu-id="6be31-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="6be31-103">응용 프로그램 도메인에서 모든 활성 스텝 퍼에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6be31-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be31-104">구문</span><span class="sxs-lookup"><span data-stu-id="6be31-104">Syntax</span></span>  
  
```  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6be31-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6be31-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="6be31-106">[out] 응용 프로그램 도메인에서 모든 활성 스텝 퍼에 대 한 열거자를 ICorDebugStepperEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6be31-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be31-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6be31-107">Requirements</span></span>  
 <span data-ttu-id="6be31-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6be31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be31-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6be31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6be31-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6be31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6be31-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
