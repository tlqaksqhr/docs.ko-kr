---
title: "ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3480761c2708fa2f15454a7a99c34e84ee34eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a>ICorProfilerCallback::ExceptionUnwindFinallyEnter 메서드
해제 단계 예외 처리를 시작 하는 프로파일러에 알립니다는 `finally` 지정된 된 함수에 포함 된 절.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 포함 된 함수 ID는 `finally` 절.  
  
## <a name="remarks"></a>설명  
 스택 가비지 수집을 허용 하는 상태가 아닐 수 있습니다 때문에이 메서드의 구현에서 프로파일러 차단 하지 않아야 하 고 따라서 선점형 가비지 수집을 사용할 수 없습니다. 이때 프로파일러가 차단 하는 경우 가비지 수집을 시도 하 고, 런타임이이 콜백이 반환 될 때까지 차단 됩니다.  
  
 이 메서드는 프로파일러 구현에는 관리 코드에 또는 관리 되는 메모리 할당에서 호출 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [GetNotifiedExceptionClauseInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [ExceptionUnwindFinallyLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
