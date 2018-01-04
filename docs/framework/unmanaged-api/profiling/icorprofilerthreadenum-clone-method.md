---
title: "ICorProfilerThreadEnum::Clone 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Clone
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d40ef6a9a666f06a46713c6295167cf5e0798ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="75a27-102">ICorProfilerThreadEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="75a27-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="75a27-103">이 파일의 복사본에 대 한 인터페이스 포인터를 가져옵니다 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="75a27-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a27-104">구문</span><span class="sxs-lookup"><span data-stu-id="75a27-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75a27-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75a27-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="75a27-106">[out] 차례로이 복사본을 가리키는 인터페이스 포인터에 대 한 포인터 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="75a27-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="75a27-107">열거자의 복사본은이 열거자와는 별도로 자체 열거형의 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="75a27-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="75a27-108">그러나 초기 커서 위치는 복사본의 열거자의 현재 커서 위치와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75a27-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a27-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75a27-109">Requirements</span></span>  
 <span data-ttu-id="75a27-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75a27-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75a27-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="75a27-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="75a27-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75a27-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75a27-113">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75a27-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a27-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75a27-114">See Also</span></span>  
 [<span data-ttu-id="75a27-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="75a27-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="75a27-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75a27-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
