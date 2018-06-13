---
title: ICorProfilerInfo2::GetBoxClassLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f046fb51753bfa79d333d465e8850794ecc73973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453540"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="2f696-102">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="2f696-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="2f696-103">지정 된 값 형식의 위치한 box이 된 경우에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f696-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f696-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f696-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f696-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2f696-106">[in] Boxed 값 형식을 설명 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2f696-107">[out] 정수는 값 형식의 boxed 개체 ID 포인터를 기준으로 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f696-108">설명</span><span class="sxs-lookup"><span data-stu-id="2f696-108">Remarks</span></span>  
 <span data-ttu-id="2f696-109">`pBufferOffset` 값은 값 형식 상자 내에서 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="2f696-110">후 `pBufferOffset` 적용 되는 boxed 개체에 값 형식의 클래스 레이아웃 데 사용할 수 개체의 값을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f696-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f696-111">Requirements</span></span>  
 <span data-ttu-id="2f696-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f696-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f696-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f696-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f696-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f696-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f696-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f696-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f696-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f696-116">See Also</span></span>  
 [<span data-ttu-id="2f696-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f696-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2f696-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f696-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
