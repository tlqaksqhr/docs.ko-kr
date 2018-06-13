---
title: ICorProfilerInfo3::EnumModules 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8045e689353a047870c1d93022132846f37dc165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453700"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="1d2a8-102">ICorProfilerInfo3::EnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="1d2a8-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="1d2a8-103">응용 프로그램에 로드되는 관리 모듈 컬렉션을 순차적으로 반복하는 메서드를 제공하는 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a8-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d2a8-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d2a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d2a8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1d2a8-106">[out] 에 대 한 포인터는 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a8-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d2a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d2a8-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d2a8-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d2a8-108">Requirements</span></span>  
 <span data-ttu-id="1d2a8-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d2a8-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d2a8-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d2a8-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d2a8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d2a8-112">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d2a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2a8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d2a8-113">See Also</span></span>  
 [<span data-ttu-id="1d2a8-114">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d2a8-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="1d2a8-115">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d2a8-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="1d2a8-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d2a8-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="1d2a8-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="1d2a8-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
