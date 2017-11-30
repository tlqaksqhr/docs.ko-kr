---
title: "ICorProfilerCallback::JITInlining 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="0a244-102">ICorProfilerCallback::JITInlining 메서드</span><span class="sxs-lookup"><span data-stu-id="0a244-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="0a244-103">Time (JIT) 컴파일러 다른 함수와 같은 줄 함수 삽입를 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a244-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a244-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a244-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a244-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="0a244-106">[in] 함수의 ID는 `calleeId` 함수 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="0a244-107">[in] 삽입 될 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="0a244-108">[out] `true` ; 되려면 삽입을 허용 하 고, 그러지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a244-109">설명</span><span class="sxs-lookup"><span data-stu-id="0a244-109">Remarks</span></span>  
 <span data-ttu-id="0a244-110">프로파일러 설정할 수 `pfShouldInline` 를 `false` 방지 하기 위해는 `calleeId` 에 삽입 되지 함수는 `callerId` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="0a244-111">또한 프로파일러 전체적으로 비활성화할 수 인라인 삽입 COR_PRF_DISABLE_INLINING 값을 사용 하 여는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0a244-112">삽입 하는 함수를 인라인으로 시작 또는 종료에 대 한 이벤트 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="0a244-113">따라서 프로파일러 설정 해야 `pfShouldInline` 를 `false` 정확한 호출 그래프를 생성 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="0a244-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="0a244-114">설정 `pfShouldInline` 를 `false` 인라인 삽입 일반적으로 속도 높이고 및 삽입 된 메서드에 대 한 별도 JIT 컴파일 이벤트의 수를 줄일 수 때문에 성능에 영향을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a244-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a244-115">Requirements</span></span>  
 <span data-ttu-id="0a244-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a244-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a244-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a244-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a244-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a244-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a244-119">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a244-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a244-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a244-120">See Also</span></span>  
 [<span data-ttu-id="0a244-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a244-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
