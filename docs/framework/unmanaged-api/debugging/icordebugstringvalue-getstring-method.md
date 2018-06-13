---
title: ICorDebugStringValue::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d3df561a3b48a4b26426235455ef1a074512f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417968"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="77144-102">ICorDebugStringValue::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="77144-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="77144-103">이 ICorDebugStringValue이 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77144-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77144-104">구문</span><span class="sxs-lookup"><span data-stu-id="77144-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77144-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77144-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="77144-106">[in] `szString` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="77144-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="77144-107">[out] 반환 된 문자 수에 대 한 포인터는 `szString` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="77144-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="77144-108">[out] 검색 된 문자열을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="77144-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77144-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77144-109">Requirements</span></span>  
 <span data-ttu-id="77144-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77144-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77144-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77144-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77144-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77144-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77144-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77144-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
