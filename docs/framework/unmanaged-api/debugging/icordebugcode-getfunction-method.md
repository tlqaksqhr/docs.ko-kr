---
title: ICorDebugCode::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d0e7f20be3f18e49dcc1b986460d5da0c3d7777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401942"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="8815e-102">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="8815e-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="8815e-103">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction을"을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8815e-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8815e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8815e-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8815e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8815e-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="8815e-106">[out] 함수의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8815e-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8815e-107">설명</span><span class="sxs-lookup"><span data-stu-id="8815e-107">Remarks</span></span>  
 <span data-ttu-id="8815e-108">`ICorDebugCode` 및 `ICorDebugFunction` 일대일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8815e-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8815e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8815e-109">Requirements</span></span>  
 <span data-ttu-id="8815e-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8815e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8815e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8815e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8815e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8815e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8815e-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8815e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8815e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8815e-114">See Also</span></span>  
 
