---
title: "COR_PRF_EX_CLAUSE_INFO 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9952ea1d8c806c9d3ac5357d933092fb82351484
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="c0bc7-102">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="c0bc7-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="c0bc7-103">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0bc7-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0bc7-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c0bc7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c0bc7-105">Members</span></span>  
  
|<span data-ttu-id="c0bc7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c0bc7-106">Member</span></span>|<span data-ttu-id="c0bc7-107">설명</span><span class="sxs-lookup"><span data-stu-id="c0bc7-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="c0bc7-108">값은 [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) 되거나 끝난 예외 절 방금 입력 한 코드의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="c0bc7-109">절 처리기의 기본 진입점-X86 EIP 레지스터의 내용을 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="c0bc7-110">절 처리기에 대 한 논리 프레임에 대 한 포인터-X86 EBP 레지스터의 내용을 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="c0bc7-111">섀도 스택 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="c0bc7-112">이 값 BSP 레지스터의 내용을 이며 IA64에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0bc7-113">설명</span><span class="sxs-lookup"><span data-stu-id="c0bc7-113">Remarks</span></span>  
 <span data-ttu-id="c0bc7-114">예외 알림이 수신 되 면 [icorprofilerinfo2:: Getnotifiedexceptionclauseinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) 예외 절에 대 한 기본 주소 및 프레임 정보를 가져오는 데 사용할 수 있습니다 (`catch` / `finally`/필터) 방금 실행 되거나 실행 하 려 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="c0bc7-115">Exception 절의 실행에는 공용 언어 런타임 (CLR)에서 이러한 콜백을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="c0bc7-116">Icorprofilercallback:: Exceptioncatcherenter</span><span class="sxs-lookup"><span data-stu-id="c0bc7-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="c0bc7-117">Icorprofilercallback:: Exceptionunwindfinallyenter</span><span class="sxs-lookup"><span data-stu-id="c0bc7-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="c0bc7-118">Icorprofilercallback:: Exceptionsearchfilterenter</span><span class="sxs-lookup"><span data-stu-id="c0bc7-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="c0bc7-119">Icorprofilercallback:: Exceptioncatcherleave</span><span class="sxs-lookup"><span data-stu-id="c0bc7-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="c0bc7-120">Icorprofilercallback:: Exceptionunwindfinallyleave</span><span class="sxs-lookup"><span data-stu-id="c0bc7-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="c0bc7-121">Icorprofilercallback:: Exceptionsearchfilterleave</span><span class="sxs-lookup"><span data-stu-id="c0bc7-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="c0bc7-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0bc7-122">Requirements</span></span>  
 <span data-ttu-id="c0bc7-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0bc7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0bc7-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c0bc7-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c0bc7-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0bc7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0bc7-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0bc7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bc7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0bc7-127">See Also</span></span>  
 [<span data-ttu-id="c0bc7-128">프로 파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="c0bc7-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
