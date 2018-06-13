---
title: ICorDebugArrayValue::HasBaseIndicies 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 574df434360dfab644a4c937dac46ebc3871a53a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399510"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="a9ee5-102">ICorDebugArrayValue::HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="a9ee5-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="a9ee5-103">이 배열의 모든 차원은 기본 0이 아닌 인덱스가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9ee5-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ee5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9ee5-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9ee5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9ee5-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="a9ee5-106">[out] 부울 값이에 대 한 포인터 `true` 경우이 하나 이상의 차원을 `ICorDebugArrayValue` 개체의 0이 아닌 기본 인덱스가 있는지, 그렇지 않으면 부울 값이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ee5-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ee5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9ee5-107">Requirements</span></span>  
 <span data-ttu-id="a9ee5-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9ee5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ee5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9ee5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9ee5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9ee5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9ee5-111">**.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ee5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
