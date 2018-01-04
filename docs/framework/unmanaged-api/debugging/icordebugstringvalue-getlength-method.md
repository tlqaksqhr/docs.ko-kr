---
title: "ICorDebugStringValue::GetLength 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 129998bc2e7530aefefb2655a83cb04a9aa4cc6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="32abe-102">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="32abe-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="32abe-103">이 ICorDebugStringValue이 참조 하는 문자열에서 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32abe-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32abe-104">구문</span><span class="sxs-lookup"><span data-stu-id="32abe-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32abe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32abe-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="32abe-106">[out] 이 참조 하는 문자열의 길이 지정 하는 값에 대 한 포인터 `ICorDebugStringValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="32abe-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32abe-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32abe-107">Requirements</span></span>  
 <span data-ttu-id="32abe-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32abe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32abe-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32abe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32abe-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32abe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32abe-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32abe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
