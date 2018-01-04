---
title: "ICorProfilerThreadEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfefb140b49a606487f1fe2bbdfb8c6a3b5c6fc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="72ed5-102">ICorProfilerThreadEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="72ed5-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="72ed5-103">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 스레드 컬렉션에서 지정된 개수의 연속 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ed5-104">구문</span><span class="sxs-lookup"><span data-stu-id="72ed5-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72ed5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72ed5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="72ed5-106">[in] 검색할 스레드 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="72ed5-107">[out] 각각 검색된 스레드를 나타내는 `ThreadID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="72ed5-108">[out] `ids` 배열에 실제로 반환된 스레드 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72ed5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="72ed5-109">Return Value</span></span>  
 <span data-ttu-id="72ed5-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="72ed5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72ed5-111">HRESULT</span></span>|<span data-ttu-id="72ed5-112">설명</span><span class="sxs-lookup"><span data-stu-id="72ed5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72ed5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="72ed5-113">S_OK</span></span>|<span data-ttu-id="72ed5-114">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="72ed5-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="72ed5-115">S_FALSE</span></span>|<span data-ttu-id="72ed5-116">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72ed5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72ed5-117">Requirements</span></span>  
 <span data-ttu-id="72ed5-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="72ed5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ed5-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72ed5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72ed5-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72ed5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72ed5-121">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ed5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ed5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72ed5-122">See Also</span></span>  
 [<span data-ttu-id="72ed5-123">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72ed5-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="72ed5-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72ed5-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
