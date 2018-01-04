---
title: "ICorDebugGCReferenceEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e61edea76b4e3be8a03000899b72d486163ceaf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="cf330-102">ICorDebugGCReferenceEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="cf330-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="cf330-103">지정된 된 수의 가져옵니다 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지 수집 되는 개체에 대 한 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cf330-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf330-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf330-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf330-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf330-105">Parameters</span></span>  
 <span data-ttu-id="cf330-106">celt</span><span class="sxs-lookup"><span data-stu-id="cf330-106">celt</span></span>  
 <span data-ttu-id="cf330-107">[in] 검색할 루트의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf330-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="cf330-108">루트</span><span class="sxs-lookup"><span data-stu-id="cf330-108">roots</span></span>  
 <span data-ttu-id="cf330-109">[out] 각각 가리키는 포인터의 배열은 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 가비지 수집 될 개체의 루트를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf330-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="cf330-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="cf330-110">pceltFetched</span></span>  
 <span data-ttu-id="cf330-111">[out] 수에 대 한 포인터 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 에 실제로 반환 된 개체 `roots`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf330-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="cf330-112">`celt`가 1이면 이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf330-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf330-113">설명</span><span class="sxs-lookup"><span data-stu-id="cf330-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf330-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf330-114">Requirements</span></span>  
 <span data-ttu-id="cf330-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf330-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf330-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf330-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf330-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf330-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf330-118">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf330-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf330-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf330-119">See Also</span></span>  
 [<span data-ttu-id="cf330-120">ICorDebugGCReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf330-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="cf330-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf330-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
