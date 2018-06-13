---
title: ICorProfilerThreadEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b803c83b905df47b3957e07c0d64e7ce6f6d303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455480"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="82226-102">ICorProfilerThreadEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="82226-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="82226-103">응용 프로그램에서 사용하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82226-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82226-104">구문</span><span class="sxs-lookup"><span data-stu-id="82226-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82226-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82226-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="82226-106">[out] 응용 프로그램에서 사용 되는 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="82226-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82226-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82226-107">Requirements</span></span>  
 <span data-ttu-id="82226-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82226-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82226-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82226-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82226-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82226-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82226-111">**.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82226-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82226-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82226-112">See Also</span></span>  
 [<span data-ttu-id="82226-113">ICorProfilerThreadEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82226-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="82226-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82226-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
