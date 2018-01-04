---
title: "ICorProfilerInfo2::GetAppDomainStaticAddress 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="3d734-102">ICorProfilerInfo2::GetAppDomainStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="3d734-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="3d734-103">지정 된 응용 프로그램 도메인의 범위에 있는 지정 된 응용 프로그램 도메인 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d734-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d734-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d734-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d734-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3d734-106">[in] 요청 된 응용 프로그램 도메인 정적 필드를 포함 하는 클래스의 클래스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3d734-107">[in] 요청한 응용 프로그램 도메인 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="3d734-108">[in] 요청 된 정적 필드에 대 한 범위는 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3d734-109">[out] 지정 된 응용 프로그램 도메인 내에 있는 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d734-110">설명</span><span class="sxs-lookup"><span data-stu-id="3d734-110">Remarks</span></span>  
 <span data-ttu-id="3d734-111">`GetAppDomainStaticAddress` 메서드에서 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="3d734-112">지정된 된 정적 필드의 주소 지정된 된 컨텍스트에서 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="3d734-113">가비지 수집 힙에서 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3d734-114">이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 수집 후 잘못 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3d734-115">클래스의 클래스 생성자 완료 되기 전에 `GetAppDomainStaticAddress` 정적 필드 중 일부를 초기화할 수 있습니다는 이미 있지만 CORPROF_E_DATAINCOMPLETE 정적의 모든 필드에 반환 하 고 가비지 수집 개체 루 팅입니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d734-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d734-116">Requirements</span></span>  
 <span data-ttu-id="3d734-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d734-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d734-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d734-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d734-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d734-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d734-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d734-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d734-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d734-121">See Also</span></span>  
 [<span data-ttu-id="3d734-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d734-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="3d734-123">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d734-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
