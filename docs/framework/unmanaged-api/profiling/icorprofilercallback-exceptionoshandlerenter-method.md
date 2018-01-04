---
title: "ICorProfilerCallback::ExceptionOSHandlerEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionOSHandlerEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c26260a2f70537deefb5600c0b721e0c0faf0399
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="e0089-102">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="e0089-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="e0089-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e0089-103">Not implemented.</span></span> <span data-ttu-id="e0089-104">관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0089-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0089-105">구문</span><span class="sxs-lookup"><span data-stu-id="e0089-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e0089-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0089-106">Requirements</span></span>  
 <span data-ttu-id="e0089-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0089-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0089-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0089-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0089-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0089-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0089-110">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0089-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0089-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0089-111">See Also</span></span>  
 [<span data-ttu-id="e0089-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0089-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
