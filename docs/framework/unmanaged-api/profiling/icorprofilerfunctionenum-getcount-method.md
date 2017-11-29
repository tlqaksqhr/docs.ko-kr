---
title: "ICorProfilerFunctionEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.GetCount Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55fff79bc68f1e2b790cf93afbce6a9f6cfd3c51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="27956-102">ICorProfilerFunctionEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="27956-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="27956-103">응용 프로그램에서 로드했거나 프로파일러에서 강제로 로드한 함수 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27956-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27956-104">구문</span><span class="sxs-lookup"><span data-stu-id="27956-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27956-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27956-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="27956-106">[out] 로드 된 함수의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27956-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27956-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27956-107">Requirements</span></span>  
 <span data-ttu-id="27956-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27956-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27956-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27956-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27956-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27956-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27956-111">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27956-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27956-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27956-112">See Also</span></span>  
 [<span data-ttu-id="27956-113">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27956-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="27956-114">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27956-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
