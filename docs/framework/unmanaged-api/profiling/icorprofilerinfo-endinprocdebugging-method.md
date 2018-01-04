---
title: "ICorProfilerInfo::EndInprocDebugging 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.EndInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a36c557d9ab2fa661808aa2f0be942d11ea9fa61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="b7d23-102">ICorProfilerInfo::EndInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="b7d23-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="b7d23-103">In-process 디버깅 세션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="b7d23-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d23-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7d23-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7d23-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7d23-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="b7d23-107">[in] 디버깅 세션을 식별 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="b7d23-108">이 값에 받은 것과 동일 해야는 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b7d23-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7d23-109">설명</span><span class="sxs-lookup"><span data-stu-id="b7d23-109">Remarks</span></span>  
 <span data-ttu-id="b7d23-110">호출 해야 [icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) 및 `EndInprocDebugging` 동일한 콜백 메서드 내에서.</span><span class="sxs-lookup"><span data-stu-id="b7d23-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="b7d23-111">CLR 디버깅 서비스 제한 in-process 디버깅.NET Framework 버전 1.0 및 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="b7d23-112">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b7d23-113">그러나 고객 의견 때문에 프로세스에서 디버깅 버전 2.0,.NET Framework에서 제거 되었으며 일련의 기능을 훨씬 더 프로 파일링 API와 같은 줄로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d23-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7d23-114">Requirements</span></span>  
 <span data-ttu-id="b7d23-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d23-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d23-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7d23-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7d23-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d23-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d23-118">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="b7d23-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d23-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7d23-119">See Also</span></span>  
 [<span data-ttu-id="b7d23-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7d23-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
