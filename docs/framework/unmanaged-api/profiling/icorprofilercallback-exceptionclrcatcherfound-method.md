---
title: "ICorProfilerCallback::ExceptionCLRCatcherFound 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f539a93b72c7bf3570dd3cf4cb484564999699c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="f47af-102">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="f47af-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="f47af-103">될 때 호출 된 `catch` 공용 언어 런타임 (CLR) 자체 내부 예외를 찾을 수에 대 한 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f47af-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="f47af-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f47af-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f47af-105">구문</span><span class="sxs-lookup"><span data-stu-id="f47af-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f47af-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f47af-106">Requirements</span></span>  
 <span data-ttu-id="f47af-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f47af-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f47af-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f47af-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f47af-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f47af-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f47af-110">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f47af-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47af-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f47af-111">See Also</span></span>  
 [<span data-ttu-id="f47af-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f47af-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f47af-113">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="f47af-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
