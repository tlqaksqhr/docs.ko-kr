---
title: ICorDebugEval::IsActive 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe29b3e35d2fbd42fac2d9ec1d1c594abe1239c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411160"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="45152-102">ICorDebugEval::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="45152-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="45152-103">ICorDebugEval 개체가이 현재 실행 되 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45152-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45152-104">구문</span><span class="sxs-lookup"><span data-stu-id="45152-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45152-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45152-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="45152-106">[out] 이 평가 활성 상태 인지 여부를 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="45152-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45152-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45152-107">Requirements</span></span>  
 <span data-ttu-id="45152-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45152-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45152-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45152-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45152-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45152-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45152-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45152-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
