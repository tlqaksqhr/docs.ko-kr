---
title: ICorProfilerInfo2::GetThreadAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 690dbb5659ce991b7c4921fbd85c246da54eff0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453043"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="27c5f-102">ICorProfilerInfo2::GetThreadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="27c5f-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="27c5f-103">지정된 된 스레드의 현재 코드를 실행 하는 응용 프로그램 도메인의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27c5f-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="27c5f-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27c5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27c5f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="27c5f-106">[in] 스레드를 지정 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="27c5f-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="27c5f-107">[out] 응용 프로그램 도메인의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27c5f-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c5f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27c5f-108">Requirements</span></span>  
 <span data-ttu-id="27c5f-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27c5f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27c5f-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27c5f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27c5f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27c5f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27c5f-112">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27c5f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c5f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27c5f-113">See Also</span></span>  
 [<span data-ttu-id="27c5f-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27c5f-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="27c5f-115">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27c5f-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
