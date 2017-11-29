---
title: "ICorProfilerCallback::ObjectAllocated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e67e6085db4b73ca39688935767072ceadb68e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated 메서드
개체에 대 한 할당 된 힙에 메모리 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 메모리가 할당 된 개체의 ID입니다.  
  
 `classId`  
 [in] 개체 인스턴스 클래스의 ID입니다.  
  
## <a name="remarks"></a>설명  
 `ObjectedAllocated` 스택 또는 관리 되지 않는 메모리에서 할당에 대 한 메서드가 호출 되지 않습니다. `classId` 매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다. 프로파일러는 해당 클래스에 대 한 클래스 부하 콜백을 받습니다 바로 뒤의 `ObjectAllocated` 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ClassLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [ClassLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
