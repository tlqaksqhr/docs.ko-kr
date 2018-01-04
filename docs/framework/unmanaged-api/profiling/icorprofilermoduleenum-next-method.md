---
title: "ICorProfilerModuleEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fca8a0f999ccc497c1929faa6cead04a1ec2774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="422aa-102">ICorProfilerModuleEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="422aa-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="422aa-103">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 모듈 컬렉션에서 지정된 개수의 연속 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="422aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="422aa-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="422aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="422aa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="422aa-106">[in] 검색할 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="422aa-107">[out] 각각 검색된 모듈을 나타내는 `ModuleID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="422aa-108">[out] `ids` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="422aa-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="422aa-109">Return Value</span></span>  
 <span data-ttu-id="422aa-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="422aa-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="422aa-111">HRESULT</span></span>|<span data-ttu-id="422aa-112">설명</span><span class="sxs-lookup"><span data-stu-id="422aa-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="422aa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="422aa-113">S_OK</span></span>|<span data-ttu-id="422aa-114">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="422aa-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="422aa-115">S_FALSE</span></span>|<span data-ttu-id="422aa-116">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="422aa-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="422aa-117">Requirements</span></span>  
 <span data-ttu-id="422aa-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="422aa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="422aa-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="422aa-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="422aa-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="422aa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="422aa-121">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="422aa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422aa-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="422aa-122">See Also</span></span>  
 [<span data-ttu-id="422aa-123">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="422aa-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="422aa-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="422aa-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
