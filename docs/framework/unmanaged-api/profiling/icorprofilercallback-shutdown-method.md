---
title: "ICorProfilerCallback::Shutdown 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown 메서드
응용 프로그램이 종료 되 고 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>설명  
 프로파일러 코드의 메서드를 안전 하 게 호출할 수 없습니다는 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 후 인터페이스는 `Shutdown` 메서드를 호출 합니다. 에 대 한 모든 호출 `ICorProfilerInfo` 메서드 후 정의 되지 않은 동작이 발생할는 `Shutdown` 메서드 반환 합니다. 종료 후 변경할 수 없는 특정 이벤트가 발생할 수 있습니다. 이렇게 되 면 즉시 반환 하는 프로파일러 주의 해야 합니다.  
  
 `Shutdown` 관리 코드로 관리 되는 응용 프로그램은 프로 파일링을 시작 하는 경우에 메서드가 호출 됩니다 (즉, 프로세스 스택의 초기 프레임은 관리 됨). 응용 프로그램 관리 되지 않는 코드로 시작 표시 되지만 나중에 관리 되는 코드로 이동 하 여 인스턴스를 만들 공용 언어 런타임 (CLR)의 다음 `Shutdown` 호출 되지 것입니다. 프로파일러 라이브러리에 포함 해야 이러한 경우에는 `DllMain` 루틴은 DLL_PROCESS_DETACH를 사용 하는 모든 리소스를 해제 하 고 추적 하 고 디스크에 플러시하는 등의 데이터 정리 프로세스를 수행할 값입니다.  
  
 일반적으로 프로파일러는 예기치 않은 종료 처리 해야 합니다. 프로세스 중단 win32의 예를 들어 `TerminateProcess` 메서드 (Winbase.h에서 선언 됨). 다른 경우에는 CLR 소멸 순서 대로 메시지를 배달 하지 않고 (백그라운드 스레드)는 특정 관리 되는 스레드를 중단 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Initialize 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
