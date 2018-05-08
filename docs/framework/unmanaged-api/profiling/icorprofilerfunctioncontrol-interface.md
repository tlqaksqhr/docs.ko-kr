---
title: ICorProfilerFunctionControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0daf772702ada9d426b3da6913fff0186e33564
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl 인터페이스
코드 프로파일러가 CLR(공용 언어 런타임)과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetCodegenFlags 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|하나 이상의 플래그 설정 된 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 다시 컴파일된 함수는-just-in-time (JIT)에 대 한 코드 생성을 제어 하는 열거형입니다.|  
|[SetILFunctionBody 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.|  
|[SetILInstrumentedCodeMap 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorProfilerFunctionControl` 인터페이스는 다시 컴파일된 단일 함수에 대한 코드 생성을 제어하는 메서드를 제공합니다. 프로파일러를 통해이 인터페이스의 인스턴스를 가져옵니다는 [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 콜백 합니다. `ICorProfilerFunctionControl`의 각 인스턴스가 단일 함수의 모든 인스턴스를 제어합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumJITedFunctions2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
