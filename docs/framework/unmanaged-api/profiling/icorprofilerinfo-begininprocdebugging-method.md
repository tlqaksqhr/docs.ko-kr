---
title: ICorProfilerInfo::BeginInprocDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82e798e1a31f771c63e71f2a85f8cbb684b237bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462392"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="8b5d3-102">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="8b5d3-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="8b5d3-103">초기화는 프로세스 디버깅을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="8b5d3-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b5d3-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b5d3-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b5d3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b5d3-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="8b5d3-107">[in] 이 값을 설정 `true` 현재 스레드만;에 대 한 디버깅 지원을 초기화할 수로 설정 `false` 모든 스레드에 대 한 디버깅 지원을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="8b5d3-108">[out] 디버깅 세션을 식별 하는 반환 된 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b5d3-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b5d3-109">Remarks</span></span>  
 <span data-ttu-id="8b5d3-110">CLR 디버깅 서비스 제한 in-process 디버깅.NET Framework 버전 1.0 및 1.1을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="8b5d3-111">디버깅 프로세스에 프로파일러를 사용 하 여 디버깅 API의 검사 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="8b5d3-112">그러나 고객 의견 때문에 프로세스에서 디버깅 버전 2.0,.NET Framework에서 제거 되었으며 일련의 기능을 훨씬 더 프로 파일링 API와 같은 줄로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b5d3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b5d3-113">Requirements</span></span>  
 <span data-ttu-id="8b5d3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b5d3-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b5d3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b5d3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b5d3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b5d3-117">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="8b5d3-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b5d3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b5d3-118">See Also</span></span>  
 [<span data-ttu-id="8b5d3-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b5d3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
