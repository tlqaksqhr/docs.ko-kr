---
title: "ICorProfilerCallback::AssemblyLoadFinished 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af5089603c2044b10061a32c5921b9eeadf86b36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="9e913-102">ICorProfilerCallback::AssemblyLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="9e913-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="9e913-103">어셈블리 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e913-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e913-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e913-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e913-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="9e913-106">[in] 로드 된 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9e913-107">[in] 어셈블리 로드를 성공적으로 완료할 지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e913-108">설명</span><span class="sxs-lookup"><span data-stu-id="9e913-108">Remarks</span></span>  
 <span data-ttu-id="9e913-109">값 `assemblyId` 될 때까지 정보 요청에 유효 하지는 `AssemblyLoadFinished` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="9e913-110">일부 요소는 어셈블리를 로드 한 후 계속 사용할 수는 `AssemblyLoadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="9e913-111">실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9e913-112">그러나 성공 HRESULT에서 `hrStatus` 어셈블리 로드의 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e913-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e913-113">Requirements</span></span>  
 <span data-ttu-id="9e913-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e913-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e913-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e913-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e913-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e913-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e913-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e913-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e913-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e913-118">See Also</span></span>  
 [<span data-ttu-id="9e913-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e913-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
