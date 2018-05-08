---
title: ICorProfilerInfo2::GetObjectGeneration 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c259bc167d2d4fbadf0d4721e3329975cb0f0caf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>ICorProfilerInfo2::GetObjectGeneration 메서드
지정 된 개체가 포함 된 힙 세그먼트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 개체의 ID입니다.  
  
 `range`  
 [out] 에 대 한 포인터는 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) 가비지 수집 중인 세대 내의 메모리 범위 (블록)를 설명 하는 구조에 있습니다. 이 범위는 지정된 된 개체를 포함합니다.  
  
## <a name="remarks"></a>설명  
 `GetObjectGeneration` 되 고 가비지 수집 중에서 있지 않으면 모든 프로파일러 콜백에서 메서드를 호출할 수 있습니다. 즉, 간에 발생 하는 제외 하 고 모든 콜백에서 호출할 수 있습니다 [icorprofilercallback2:: Garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) 및 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
