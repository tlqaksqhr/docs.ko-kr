---
title: ICorDebugGenericValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83aebad108a743d25b8ea93c99060d10bf5c3980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413210"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="61308-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="61308-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="61308-103">지정된 된 버퍼에서 새 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="61308-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61308-104">구문</span><span class="sxs-lookup"><span data-stu-id="61308-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61308-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61308-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="61308-106">[in] 값을 복사할 대상 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="61308-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61308-107">설명</span><span class="sxs-lookup"><span data-stu-id="61308-107">Remarks</span></span>  
 <span data-ttu-id="61308-108">참조 형식의 경우 값은 콘텐츠가 아니라 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="61308-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61308-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61308-109">Requirements</span></span>  
 <span data-ttu-id="61308-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61308-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61308-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61308-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61308-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61308-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61308-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61308-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
