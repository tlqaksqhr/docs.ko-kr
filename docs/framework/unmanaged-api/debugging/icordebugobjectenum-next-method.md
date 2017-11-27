---
title: "ICorDebugObjectEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72195dbf74639d5799bb96754019dddf0f30101a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="2619f-102">ICorDebugObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="2619f-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="2619f-103">현재 위치부터 시작 하는 열거형에서 지정 된 개수의 개체의 상대 가상 주소를 (Rva)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2619f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2619f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2619f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2619f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2619f-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="2619f-107">[out] CORDB_ADDRESS 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2619f-108">[out] 실제로 반환 된 개체의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="2619f-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2619f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2619f-110">Requirements</span></span>  
 <span data-ttu-id="2619f-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2619f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2619f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2619f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2619f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2619f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2619f-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2619f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2619f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2619f-115">See Also</span></span>  
 
