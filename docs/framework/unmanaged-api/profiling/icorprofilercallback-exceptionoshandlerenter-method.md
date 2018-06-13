---
title: ICorProfilerCallback::ExceptionOSHandlerEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2dc7c22ee075f347604864d8bee1a4e871da616
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451768"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="666f1-102">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="666f1-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="666f1-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="666f1-103">Not implemented.</span></span> <span data-ttu-id="666f1-104">관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666f1-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666f1-105">구문</span><span class="sxs-lookup"><span data-stu-id="666f1-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="666f1-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="666f1-106">Requirements</span></span>  
 <span data-ttu-id="666f1-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="666f1-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666f1-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="666f1-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="666f1-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="666f1-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="666f1-110">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666f1-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666f1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="666f1-111">See Also</span></span>  
 [<span data-ttu-id="666f1-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="666f1-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
