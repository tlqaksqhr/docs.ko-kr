---
title: ICorProfilerCallback2::GarbageCollectionStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a447dca98e5010163d5cc5f4f3da4333f4cdf7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455272"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted 메서드
가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cGenerations`  
 [in] 에 있는 항목의 총 수는 `generationCollected` 배열입니다.  
  
 `generationCollected`  
 [in] 되는 부울 값의 배열을 `true` 세대 인덱스에 해당 하 고, 그렇지 않으면이 가비지 수집에 의해 수집 되 고 있으면 `false`합니다.  
  
 배열의 값을 기준으로 인덱싱되어 있으면는 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) 생성을 나타내는 열거형입니다.  
  
 `reason`  
 [in] 값은 [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) 가비지 수집 이유를 나타내는 열거형에서 발생 했습니다.  
  
## <a name="remarks"></a>설명  
 이 가비지 컬렉션에 속하는 모든 콜백이 간에 발생 합니다는 `GarbageCollectionStarted` 콜백 및 해당 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 콜백 합니다. 이러한 콜백은 동일한 스레드에서 발생 하지 않아도 됩니다.  
  
 이 하는 동안 원래 위치에 개체 검사를 프로파일러에 대 한 안전는 `GarbageCollectionStarted` 콜백 합니다. 가비지 수집기에서 반환 된 후 개체 이동을 시작 됩니다 `GarbageCollectionStarted`합니다. 프로파일러 모든 개체 Id를 받을 때까지 유효 하지 않은 것을 고려해 야이 콜백에서 반환 된, 후는 `ICorProfilerCallback2::GarbageCollectionFinished` 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
