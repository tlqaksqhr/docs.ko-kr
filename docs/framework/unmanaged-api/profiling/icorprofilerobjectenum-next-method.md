---
title: "ICorProfilerObjectEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a82a3c6c3de012db6f187bdd7ea3b9e2eebb86b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="c8c8b-102">ICorProfilerObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c8c8b-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="c8c8b-103">시퀀스에서 열거자의 현재 위치부터 시작 하는 개체의 순차적인 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8c8b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8c8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8c8b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c8c8b-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c8c8b-107">[out] 배열 `ObjectID` 각각 검색 된 개체를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c8c8b-108">[out] `objects` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c8b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8c8b-109">Requirements</span></span>  
 <span data-ttu-id="c8c8b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8c8b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c8b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8c8b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8c8b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8c8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8c8b-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c8b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8c8b-114">See Also</span></span>  
 [<span data-ttu-id="c8c8b-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8c8b-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
