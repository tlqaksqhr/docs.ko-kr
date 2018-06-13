---
title: ICorProfilerModuleEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9249e6f5ee7b15d55f5518263b0ac2e31b64e993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454462"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="518aa-102">ICorProfilerModuleEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="518aa-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="518aa-103">이 파일의 복사본에 대 한 인터페이스 포인터를 가져옵니다 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="518aa-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="518aa-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="518aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="518aa-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="518aa-106">[out] 이 복사본을 가리키고 있는 인터페이스 포인터에 대 한 포인터 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="518aa-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="518aa-107">열거자의 복사본은이 열거자와는 별도로 자체 열거형의 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="518aa-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="518aa-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="518aa-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518aa-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="518aa-109">Requirements</span></span>  
 <span data-ttu-id="518aa-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="518aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518aa-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="518aa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="518aa-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="518aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="518aa-113">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518aa-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="518aa-114">See Also</span></span>  
 [<span data-ttu-id="518aa-115">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="518aa-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="518aa-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="518aa-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
