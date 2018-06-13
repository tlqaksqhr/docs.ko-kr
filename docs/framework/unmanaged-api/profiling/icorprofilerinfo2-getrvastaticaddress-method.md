---
title: ICorProfilerInfo2::GetRVAStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ee12131cfa323d4426ab06ea31be4a8dd7b4583
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455467"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="a44d5-102">ICorProfilerInfo2::GetRVAStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="a44d5-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="a44d5-103">지정 된 상대 가상 주소 (RVA) 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a44d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a44d5-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a44d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a44d5-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a44d5-106">[in] 요청 된 RVA 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="a44d5-107">[in] 요청 된 RVA 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="a44d5-108">[out] RVA 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a44d5-109">설명</span><span class="sxs-lookup"><span data-stu-id="a44d5-109">Remarks</span></span>  
 <span data-ttu-id="a44d5-110">`GetRVAStaticAddress` 메서드에서 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="a44d5-111">지정된 된 정적 필드의 주소 지정된 된 컨텍스트에서 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="a44d5-112">가비지 수집 힙에서 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="a44d5-113">이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 수집 후 잘못 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="a44d5-114">클래스의 클래스 생성자 완료 되기 전에 `GetRVAStaticAddress` 정적 필드 중 일부를 이미 초기화 될 수 있습니다 및 가비지 컬렉션 개체를 루 팅 있지만 CORPROF_E_DATAINCOMPLETE 정적의 모든 필드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a44d5-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a44d5-115">Requirements</span></span>  
 <span data-ttu-id="a44d5-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a44d5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a44d5-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a44d5-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a44d5-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a44d5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a44d5-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a44d5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44d5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a44d5-120">See Also</span></span>  
 [<span data-ttu-id="a44d5-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a44d5-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="a44d5-122">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a44d5-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
