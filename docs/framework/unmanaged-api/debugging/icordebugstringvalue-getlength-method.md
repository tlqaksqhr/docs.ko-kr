---
title: ICorDebugStringValue::GetLength 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e62539304817432fcab8f3e0958e5a70b371b83d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416949"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="64a80-102">ICorDebugStringValue::GetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="64a80-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="64a80-103">이 ICorDebugStringValue이 참조 하는 문자열에서 문자 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64a80-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a80-104">구문</span><span class="sxs-lookup"><span data-stu-id="64a80-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64a80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64a80-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="64a80-106">[out] 이 참조 하는 문자열의 길이 지정 하는 값에 대 한 포인터 `ICorDebugStringValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="64a80-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a80-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64a80-107">Requirements</span></span>  
 <span data-ttu-id="64a80-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64a80-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a80-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64a80-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64a80-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64a80-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64a80-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a80-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
