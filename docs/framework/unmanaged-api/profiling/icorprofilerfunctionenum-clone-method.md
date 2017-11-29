---
title: "ICorProfilerFunctionEnum::Clone 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Clone Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dc1d14a1480c3634993190448f9beff911bebf6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="ccc73-102">ICorProfilerFunctionEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="ccc73-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="ccc73-103">이 파일의 복사본에 대 한 인터페이스 포인터를 가져옵니다 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ccc73-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc73-104">구문</span><span class="sxs-lookup"><span data-stu-id="ccc73-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccc73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccc73-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="ccc73-106">[out] 차례로이 복사본을 가리키는 인터페이스 포인터에 대 한 포인터 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ccc73-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="ccc73-107">열거자의 복사본은이 열거자와는 별도로 자체 열거형의 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc73-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="ccc73-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc73-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc73-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccc73-109">Requirements</span></span>  
 <span data-ttu-id="ccc73-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc73-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc73-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccc73-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccc73-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccc73-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccc73-113">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc73-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc73-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccc73-114">See Also</span></span>  
 [<span data-ttu-id="ccc73-115">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccc73-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="ccc73-116">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccc73-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
