---
title: ICorDebugCode::IsIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccebe01c853677f7c78731e757ef7a5f090d6919
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415193"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0400f-102">ICorDebugCode::IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="0400f-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="0400f-103">이 "ICorDebugCode" Microsoft intermediate language (MSIL)에서 컴파일된 코드를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0400f-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0400f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0400f-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0400f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0400f-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="0400f-106">[out] `true` 이 `ICorDebugCode` 고, 그러지 않으면 MSIL에 컴파일된 코드를 나타내는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0400f-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0400f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0400f-107">Requirements</span></span>  
 <span data-ttu-id="0400f-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0400f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0400f-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0400f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0400f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0400f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0400f-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0400f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0400f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0400f-112">See Also</span></span>  
 
