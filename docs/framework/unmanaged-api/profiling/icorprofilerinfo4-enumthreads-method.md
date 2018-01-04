---
title: "ICorProfilerInfo4::EnumThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.EnumThreads
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e4dc301458d87b08960ef7c0b64203c703491ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="5d1c2-102">ICorProfilerInfo4::EnumThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="5d1c2-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="5d1c2-103">프로 파일링된 프로세스의 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1c2-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d1c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d1c2-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d1c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d1c2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5d1c2-106">[out] 에 대 한 포인터는 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d1c2-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d1c2-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d1c2-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1c2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d1c2-108">Requirements</span></span>  
 <span data-ttu-id="5d1c2-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1c2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d1c2-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d1c2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d1c2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d1c2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d1c2-112">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1c2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d1c2-113">See Also</span></span>  
 [<span data-ttu-id="5d1c2-114">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d1c2-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="5d1c2-115">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d1c2-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="5d1c2-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d1c2-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="5d1c2-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="5d1c2-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
