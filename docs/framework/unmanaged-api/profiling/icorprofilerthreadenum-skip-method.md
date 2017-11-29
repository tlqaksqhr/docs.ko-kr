---
title: "ICorProfilerThreadEnum::Skip 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f492a455165f3b49994beb3220334e2932bf214c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="60588-102">ICorProfilerThreadEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="60588-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="60588-103">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="60588-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60588-104">구문</span><span class="sxs-lookup"><span data-stu-id="60588-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60588-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60588-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="60588-106">[in] 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="60588-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60588-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="60588-107">Return Value</span></span>  
 <span data-ttu-id="60588-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="60588-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="60588-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60588-109">HRESULT</span></span>|<span data-ttu-id="60588-110">설명</span><span class="sxs-lookup"><span data-stu-id="60588-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60588-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="60588-111">S_OK</span></span>|<span data-ttu-id="60588-112">`celt`요소를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="60588-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="60588-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="60588-113">S_FALSE</span></span>|<span data-ttu-id="60588-114">보다 적은 `celt` 요소, 해당 주소는 더 이상 요소가 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60588-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60588-115">설명</span><span class="sxs-lookup"><span data-stu-id="60588-115">Remarks</span></span>  
 <span data-ttu-id="60588-116">이 열거자의이 커서는 새 위치는 (현재 위치) + `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="60588-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60588-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60588-117">Requirements</span></span>  
 <span data-ttu-id="60588-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60588-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60588-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60588-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60588-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60588-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60588-121">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60588-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60588-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60588-122">See Also</span></span>  
 [<span data-ttu-id="60588-123">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60588-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="60588-124">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60588-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
