---
title: "ICorDebugObjectEnum::Next 메서드"
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
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c8edc9273710a843b4e99568097646825fc52a09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="64cb9-102">ICorDebugObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="64cb9-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="64cb9-103">현재 위치부터 시작 하는 열거형에서 지정 된 개수의 개체의 상대 가상 주소를 (Rva)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64cb9-104">구문</span><span class="sxs-lookup"><span data-stu-id="64cb9-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64cb9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64cb9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="64cb9-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="64cb9-107">[out] CORDB_ADDRESS 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="64cb9-108">[out] 실제로 반환 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="64cb9-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64cb9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64cb9-110">Requirements</span></span>  
 <span data-ttu-id="64cb9-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64cb9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64cb9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64cb9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64cb9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64cb9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64cb9-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64cb9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cb9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64cb9-115">See Also</span></span>  
 
