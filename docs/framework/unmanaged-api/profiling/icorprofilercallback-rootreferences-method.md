---
title: "ICorProfilerCallback::RootReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd057538450deeb46a72178c725103e04a8dd126
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences 메서드
가비지 수집 후 루트 참조에 대 한 정보를 프로파일러를에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cRootRefs`  
 [in] 에 대 한 참조 횟수는 `rootRefIds` 배열입니다.  
  
 `rootRefIds`  
 [in] 스택에 개체 또는 정적 개체가 참조 하는 개체 Id의 배열입니다.  
  
## <a name="remarks"></a>설명  
 둘 다 `RootReferences` 및 [icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 프로파일러에 알리기 위해 호출 됩니다. 하나 또는 다른 프로파일러 일반적으로 구현 둘 정보에 전달 되므로 `RootReferences2` 전달의 상위 집합 `RootReferences`합니다.  
  
 에 대 한 수의 `rootRefIds` null 개체가 포함 될 배열입니다. 예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에서 루트로 처리 되 고 항상 보고 됩니다.  
  
 반환 된 개체 Id `RootReferences` 가비지 수집 이전 주소에서 새 주소 개체를 이동 하는 중일 수 있으므로 콜백 하는 동안 유효 하지 않습니다. 따라서 프로파일러 마십시오 중에 개체 검사는 `RootReferences` 호출 합니다. 때 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 은 호출 개체를 모두 새 위치로 이동 되었고 안전 하 게 검사할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
