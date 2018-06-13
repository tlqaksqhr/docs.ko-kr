---
title: ICorProfilerInfo::GetInprocInspectionIThisThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d603d9bc7a343a41224cf8d889a69823875d9db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453592"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="655ae-102">ICorProfilerInfo::GetInprocInspectionIThisThread 메서드</span><span class="sxs-lookup"><span data-stu-id="655ae-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="655ae-103">ICorDebugThread 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="655ae-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655ae-105">구문</span><span class="sxs-lookup"><span data-stu-id="655ae-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="655ae-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="655ae-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="655ae-107">[out](/cpp/atl/iunknown) 에 대해 쿼리할 수 있는 개체는 `ICorDebugThread` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="655ae-108">설명</span><span class="sxs-lookup"><span data-stu-id="655ae-108">Remarks</span></span>  
 <span data-ttu-id="655ae-109">디버깅 서비스 공용 언어 런타임 (CLR).NET Framework 버전 1.0에서에서 제한 된 in-process 디버깅이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="655ae-110">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="655ae-111">고객 의견의 결과로 in-process 디버깅 버전 2.0,.NET Framework에서 제거 되었으며 일련의 기능을 훨씬 더 프로 파일링 API와 같은 줄로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655ae-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="655ae-112">Requirements</span></span>  
 <span data-ttu-id="655ae-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="655ae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655ae-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="655ae-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="655ae-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="655ae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="655ae-116">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="655ae-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655ae-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="655ae-117">See Also</span></span>  
 [<span data-ttu-id="655ae-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="655ae-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
