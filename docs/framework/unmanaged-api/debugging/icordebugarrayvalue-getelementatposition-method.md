---
title: "ICorDebugArrayValue::GetElementAtPosition 메서드"
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
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c26a55815e57126895902275148940c5271c235b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="3b233-102">ICorDebugArrayValue::GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="3b233-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="3b233-103">배열의 0부터 시작 하는 단일 차원 배열로 처리 하는 방법, 지정된 된 위치에 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b233-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b233-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b233-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b233-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b233-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="3b233-106">[in] 검색할 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3b233-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3b233-107">[out] 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b233-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b233-108">설명</span><span class="sxs-lookup"><span data-stu-id="3b233-108">Remarks</span></span>  
 <span data-ttu-id="3b233-109">다차원 배열의 레이아웃 배열 레이아웃의 c + + 스타일을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b233-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b233-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b233-110">Requirements</span></span>  
 <span data-ttu-id="3b233-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3b233-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b233-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b233-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b233-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b233-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b233-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b233-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
