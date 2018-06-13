---
title: ICorDebugValueEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 433e387365834498203e444ed2f85889f8adde06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420447"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="530e7-102">ICorDebugValueEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="530e7-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="530e7-103">현재 위치부터 시작 하는 열거형에서 지정 된 "ICorDebugValue" 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="530e7-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="530e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="530e7-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="530e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="530e7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="530e7-106">[in] 수가 `ICorDebugValue` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="530e7-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="530e7-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="530e7-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="530e7-108">[out] 수에 대 한 포인터 `ICorDebugValue` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="530e7-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="530e7-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="530e7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="530e7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="530e7-110">Requirements</span></span>  
 <span data-ttu-id="530e7-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="530e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530e7-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="530e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="530e7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="530e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="530e7-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="530e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530e7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="530e7-115">See Also</span></span>  
    
 
