---
title: "ICorProfilerCallback::AppDomainCreationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 395664081460677c4d2b94fc5478513ce239c5be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="19abc-102">ICorProfilerCallback::AppDomainCreationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="19abc-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="19abc-103">응용 프로그램 도메인 생성 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="19abc-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19abc-104">구문</span><span class="sxs-lookup"><span data-stu-id="19abc-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19abc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19abc-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="19abc-106">[in] 생성 되 고 도메인을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="19abc-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19abc-107">설명</span><span class="sxs-lookup"><span data-stu-id="19abc-107">Remarks</span></span>  
 <span data-ttu-id="19abc-108">ID 정보 요청 될 때까지 적합 하지 않습니다는 [icorprofilercallback:: Appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="19abc-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19abc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19abc-109">Requirements</span></span>  
 <span data-ttu-id="19abc-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19abc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19abc-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19abc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19abc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19abc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19abc-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19abc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19abc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19abc-114">See Also</span></span>  
 [<span data-ttu-id="19abc-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19abc-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
