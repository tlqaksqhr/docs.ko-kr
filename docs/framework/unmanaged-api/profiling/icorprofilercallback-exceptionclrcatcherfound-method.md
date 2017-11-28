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
ms.openlocfilehash: ebb1779ca9f09089a071673f92810ea7a9e76b3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="9a43c-102">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="9a43c-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="9a43c-103">될 때 호출 된 `catch` 공용 언어 런타임 (CLR) 자체 내부 예외를 찾을 수에 대 한 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a43c-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="9a43c-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a43c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a43c-105">구문</span><span class="sxs-lookup"><span data-stu-id="9a43c-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9a43c-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a43c-106">Requirements</span></span>  
 <span data-ttu-id="9a43c-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a43c-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a43c-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a43c-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a43c-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a43c-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a43c-110">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="9a43c-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a43c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a43c-111">See Also</span></span>  
 [<span data-ttu-id="9a43c-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a43c-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9a43c-113">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="9a43c-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
