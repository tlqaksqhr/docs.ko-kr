---
title: "ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b63f428cd75ed98d30e4b6ecca69dbe3b5b5656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="6dc41-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="6dc41-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="6dc41-103">될 때 호출 된 `catch` 차단 예외가 공용 언어 런타임 (CLR) 자체 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dc41-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="6dc41-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc41-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc41-105">구문</span><span class="sxs-lookup"><span data-stu-id="6dc41-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="6dc41-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6dc41-106">Requirements</span></span>  
 <span data-ttu-id="6dc41-107">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc41-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc41-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6dc41-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6dc41-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dc41-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dc41-110">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6dc41-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc41-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dc41-111">See Also</span></span>  
 [<span data-ttu-id="6dc41-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6dc41-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6dc41-113">ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="6dc41-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
