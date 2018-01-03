---
title: "ICorDebugCode::GetAddress 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20fe5f76e36eb7f5e59f650bc813aea8ad455078
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="52828-102">ICorDebugCode::GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="52828-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="52828-103">이 "ICorDebugCode" 인터페이스를 나타내는 코드 세그먼트의 (RVA) 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52828-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52828-104">구문</span><span class="sxs-lookup"><span data-stu-id="52828-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52828-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52828-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="52828-106">[out] 코드 세그먼트의 RVA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="52828-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52828-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52828-107">Requirements</span></span>  
 <span data-ttu-id="52828-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52828-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52828-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52828-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52828-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52828-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52828-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52828-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52828-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52828-112">See Also</span></span>  
 
