---
title: "ICorDebugTypeEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38f48c379ad4d84c2b16c208b33b71ac75caa52f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="6aa8c-102">ICorDebugTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="6aa8c-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="6aa8c-103">로 지정 된 "ICorDebugType" 인스턴스 수를 가져옵니다 `celt` 에서 현재 위치부터 시작 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6aa8c-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6aa8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6aa8c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6aa8c-106">[in] 수가 `ICorDebugType` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="6aa8c-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugType` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6aa8c-108">[out] 수에 대 한 포인터 `ICorDebugType` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="6aa8c-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa8c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6aa8c-110">Requirements</span></span>  
 <span data-ttu-id="6aa8c-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa8c-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aa8c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aa8c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aa8c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aa8c-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa8c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa8c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6aa8c-115">See Also</span></span>  
 
