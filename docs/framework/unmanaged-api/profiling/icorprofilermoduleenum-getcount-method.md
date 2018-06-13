---
title: ICorProfilerModuleEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91572887713216f94707e5d21e5767f4cc54e0d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456260"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="92151-102">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="92151-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="92151-103">응용 프로그램에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92151-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92151-104">구문</span><span class="sxs-lookup"><span data-stu-id="92151-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92151-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92151-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="92151-106">[out] 컬렉션에 대 한 런타임 모듈의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="92151-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92151-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92151-107">Requirements</span></span>  
 <span data-ttu-id="92151-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92151-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92151-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92151-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92151-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92151-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92151-111">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92151-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92151-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92151-112">See Also</span></span>  
 [<span data-ttu-id="92151-113">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92151-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="92151-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92151-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
