---
title: "ICorProfilerInfo2::GetBoxClassLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetBoxClassLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c11013781a4fc8f627dac97894ff9ef02bfda51c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="a7015-102">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="a7015-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="a7015-103">지정 된 값 형식의 위치한 box이 된 경우에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7015-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7015-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7015-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7015-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a7015-106">[in] Boxed 값 형식을 설명 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="a7015-107">[out] 정수는 값 형식의 boxed 개체 ID 포인터를 기준으로 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7015-108">설명</span><span class="sxs-lookup"><span data-stu-id="a7015-108">Remarks</span></span>  
 <span data-ttu-id="a7015-109">`pBufferOffset` 값은 값 형식 상자 내에서 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="a7015-110">후 `pBufferOffset` 적용 되는 boxed 개체에 값 형식의 클래스 레이아웃 데 사용할 수 개체의 값을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7015-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7015-111">Requirements</span></span>  
 <span data-ttu-id="a7015-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7015-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7015-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7015-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7015-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7015-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7015-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7015-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7015-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7015-116">See Also</span></span>  
 [<span data-ttu-id="a7015-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7015-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="a7015-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7015-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
