---
title: "ICorDebugCode::GetFunction 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0304eaadec5805b1ded9a4cbfe79959c3e18a344
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="f5687-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="f5687-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="f5687-103">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction을"을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5687-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5687-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5687-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5687-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5687-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="f5687-106">[out] 함수의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f5687-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5687-107">설명</span><span class="sxs-lookup"><span data-stu-id="f5687-107">Remarks</span></span>  
 <span data-ttu-id="f5687-108">`ICorDebugCode`및 `ICorDebugFunction` 일대일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5687-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5687-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5687-109">Requirements</span></span>  
 <span data-ttu-id="f5687-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5687-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5687-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5687-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5687-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5687-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5687-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5687-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5687-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5687-114">See Also</span></span>  
 
