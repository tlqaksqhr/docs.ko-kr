---
title: "ICorProfilerInfo3::GetThreadStaticAddress2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d657f0d6a28f19c45910fa354b7b40822ad12947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="9233d-102">ICorProfilerInfo3::GetThreadStaticAddress2 메서드</span><span class="sxs-lookup"><span data-stu-id="9233d-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="9233d-103">지정된 스레드 및 응용 프로그램 도메인의 범위에 있는 지정된 Thread 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9233d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9233d-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9233d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9233d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="9233d-106">[in] 요청 된 thread 정적 필드를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="9233d-107">[in] 요청 된 thread 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="9233d-108">[in] 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="9233d-109">[in] 요청 된 정적 필드에 대 한 범위를 한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="9233d-110">[out] 지정 된 스레드 내에 있는 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9233d-111">설명</span><span class="sxs-lookup"><span data-stu-id="9233d-111">Remarks</span></span>  
 <span data-ttu-id="9233d-112">`GetThreadStaticAddress2` 메서드에서 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="9233d-113">지정된 된 정적 필드의 주소 지정된 된 컨텍스트에서 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="9233d-114">가비지 수집 힙에서 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="9233d-115">이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 수집 후 잘못 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="9233d-116">클래스의 클래스 생성자 완료 되기 전에 `GetThreadStaticAddress2` 정적 필드 중 일부를 초기화할 수 있습니다는 이미 있지만 CORPROF_E_DATAINCOMPLETE 정적의 모든 필드에 반환 하 고 가비지 수집 개체 루 팅입니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="9233d-117">[icorprofilerinfo2:: Getthreadstaticaddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) 메서드는 비슷합니다는 `GetThreadStaticAddress2` 메서드를 하지만 응용 프로그램 도메인 인수를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9233d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9233d-118">Requirements</span></span>  
 <span data-ttu-id="9233d-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9233d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9233d-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9233d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9233d-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9233d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9233d-122">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9233d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9233d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9233d-123">See Also</span></span>  
 [<span data-ttu-id="9233d-124">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9233d-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="9233d-125">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9233d-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="9233d-126">프로파일링</span><span class="sxs-lookup"><span data-stu-id="9233d-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
