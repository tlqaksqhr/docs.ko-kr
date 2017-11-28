---
title: "ICorProfilerCallback::ExceptionOSHandlerLeave 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionOSHandlerLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98596fd640437639ee3d5ffad4bce8503f5f5e44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="01d1d-102">ICorProfilerCallback::ExceptionOSHandlerLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="01d1d-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="01d1d-103">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="01d1d-103">Not implemented.</span></span> <span data-ttu-id="01d1d-104">관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d1d-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01d1d-105">구문</span><span class="sxs-lookup"><span data-stu-id="01d1d-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="01d1d-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01d1d-106">Requirements</span></span>  
 <span data-ttu-id="01d1d-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01d1d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01d1d-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01d1d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01d1d-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01d1d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01d1d-110">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01d1d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d1d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01d1d-111">See Also</span></span>  
 [<span data-ttu-id="01d1d-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01d1d-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
