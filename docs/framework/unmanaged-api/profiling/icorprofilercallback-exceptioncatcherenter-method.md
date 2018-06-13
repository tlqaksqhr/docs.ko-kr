---
title: ICorProfilerCallback::ExceptionCatcherEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450832"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter 메서드
컨트롤을 적절 한 전달 되는 프로파일러에 알립니다 `catch` 블록입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 포함 하는 함수 식별자는 `catch` 블록입니다.  
  
 `objectId`  
 [in] 처리 되 고 예외의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 `ExceptionCatcherEnter` 타임 (JIT) 컴파일러를 사용 하 여 컴파일된 코드에서 catch 포인터가 있는 경우에 메서드가 호출 됩니다. 런타임에서의 내부 코드에 또는 비관리 코드에서 발견 된 예외는이 알림을 호출 하지 않습니다. `objectId` 가비지 수집 이후 개체 이동 되었으면 있으므로 값이 다시 전달 된 `ExceptionThrown` 알림입니다.  
  
 스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다. 이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.  
  
 이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ExceptionCatcherLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
