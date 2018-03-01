---
title: "ICorProfilerCallback4::GetReJITParameters 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03e5440fbd016f52642a5626b0cf0b82e7ecea45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters 메서드
새 다시 컴파일된 메서드 본문에 대 한 대체 코드 생성 플래그를 설정 하려면 코드 프로파일러를 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] CLR JIT 다시 컴파일을 매개 변수를 필요한 메서드를 포함 하는 모듈입니다.  
  
 `methodId`  
 [in] `MethodDef` 메서드의 CLR JIT 다시 컴파일을 매개 변수를 필요 합니다.  
  
 `pFunctionControl`  
 [in] 에 대 한 포인터는 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 프로파일러 컴파일할 메서드에 대 한 JIT 다시 컴파일을 정보를 제공 하는 데 사용할 수 있는 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 CLR 문제는 `GetReJITParameters` 콜백 프로파일러는 지정 된 메서드를 다시 컴파일할 수에 대 한 매개 변수를 지정할 수 있도록 합니다. `GetReJITParameters` 콜백 함수 당 한 번만 실행 될 있으며 프로파일러에서 제공 된 매개 변수는 해당 함수의 모든 인스턴스에 적용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [ReJITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
