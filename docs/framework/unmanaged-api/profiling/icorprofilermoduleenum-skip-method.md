---
title: ICorProfilerModuleEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35256a25ed793ffee6ddc1b26088e0988fea5af2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454348"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="5d83e-102">ICorProfilerModuleEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="5d83e-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="5d83e-103">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d83e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d83e-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d83e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d83e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5d83e-106">[in] 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d83e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5d83e-107">Return Value</span></span>  
 <span data-ttu-id="5d83e-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5d83e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d83e-109">HRESULT</span></span>|<span data-ttu-id="5d83e-110">설명</span><span class="sxs-lookup"><span data-stu-id="5d83e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d83e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d83e-111">S_OK</span></span>|<span data-ttu-id="5d83e-112">`celt` 요소를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5d83e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5d83e-113">S_FALSE</span></span>|<span data-ttu-id="5d83e-114">보다 적은 `celt` 요소, 해당 주소는 더 이상 요소가 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d83e-115">설명</span><span class="sxs-lookup"><span data-stu-id="5d83e-115">Remarks</span></span>  
 <span data-ttu-id="5d83e-116">이 열거자의이 커서는 새 위치는 (현재 위치) + `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d83e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d83e-117">Requirements</span></span>  
 <span data-ttu-id="5d83e-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d83e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d83e-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d83e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d83e-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d83e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d83e-121">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d83e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d83e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d83e-122">See Also</span></span>  
 [<span data-ttu-id="5d83e-123">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d83e-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="5d83e-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d83e-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
