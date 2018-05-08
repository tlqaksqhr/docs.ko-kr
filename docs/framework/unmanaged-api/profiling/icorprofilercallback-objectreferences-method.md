---
title: ICorProfilerCallback::ObjectReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e64eeff8ef80aa264c9c49bd12a0cc45e0da18a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences 메서드
지정된 된 개체에서 참조 하는 메모리에 개체에 대 한 프로파일러를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 개체를 참조 하는 개체의 ID입니다.  
  
 `classId`  
 [in] 지정된 된 개체의 인스턴스가 있는 클래스의 ID입니다.  
  
 `cObjectRefs`  
 [in] 지정된 된 개체에서 참조 하는 개체 수 (즉,에 있는 요소의 수는 `objectRefIds` 배열)입니다.  
  
 `objectRefIds`  
 [in] 참조 하는 개체의 Id 배열을 `objectId`합니다.  
  
## <a name="remarks"></a>설명  
 `ObjectReferences` 힙에 남아 있는 가비지 수집이 완료 된 후 각 개체에 대 한 메서드 호출 됩니다. 프로파일러가이 콜백에서 오류를 반환 하는 경우 다음 가비지 수집 될 때까지이 콜백이 호출에서는 프로 파일링 서비스 중단 됩니다.  
  
 `ObjectReferences` 콜백와 함께에서 사용할 수는 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 런타임에 대 한 완전 한 개체 참조 그래프를 만들 콜백입니다. 공용 언어 런타임 (CLR)를 사용 하면 각 개체 참조 하 여 한 번만 보고 됩니다는 `ObjectReferences` 메서드.  
  
 반환 된 개체 Id `ObjectReferences` 가비지 수집에서 개체를 이동 하는 중일 수 있으므로 콜백 하는 동안 유효 하지 않습니다. 따라서 프로파일러 마십시오 중에 개체 검사는 `ObjectReferences` 호출 합니다. 때 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 호출 되는 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.  
  
 Null `ClassId` 나타냅니다 `objectId` 언로드되고 형식이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
