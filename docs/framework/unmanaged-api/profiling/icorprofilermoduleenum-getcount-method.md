---
title: "ICorProfilerModuleEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.GetCount Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 930184a1d5c68ea87b2e3bc62b44a0176cd9db06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="2e957-102">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2e957-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="2e957-103">응용 프로그램에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2e957-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e957-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e957-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e957-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e957-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2e957-106">[out] 컬렉션에 대 한 런타임 모듈의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2e957-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e957-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e957-107">Requirements</span></span>  
 <span data-ttu-id="2e957-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e957-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e957-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e957-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2e957-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e957-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e957-111">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e957-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e957-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e957-112">See Also</span></span>  
 [<span data-ttu-id="2e957-113">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e957-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="2e957-114">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e957-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
