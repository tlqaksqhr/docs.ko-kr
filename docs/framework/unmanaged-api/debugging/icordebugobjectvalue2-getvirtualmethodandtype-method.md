---
title: "ICorDebugObjectValue2::GetVirtualMethodAndType 메서드"
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
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae45088a95b887e10fef66b5c6feab57393c6c29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="77523-102">ICorDebugObjectValue2::GetVirtualMethodAndType 메서드</span><span class="sxs-lookup"><span data-stu-id="77523-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="77523-103">이 메서드는 아직 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="77523-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77523-104">구문</span><span class="sxs-lookup"><span data-stu-id="77523-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="77523-105">설명</span><span class="sxs-lookup"><span data-stu-id="77523-105">Remarks</span></span>  
 <span data-ttu-id="77523-106">가장 많이 파생 된 메서드 및 지정 된 멤버 참조에 대 한 형식을 나타내는 "ICorDebugFunction" 및 "ICorDebugType" 인스턴스에 대 한 포인터의 인터페이스 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77523-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77523-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77523-107">See Also</span></span>  
    
 
