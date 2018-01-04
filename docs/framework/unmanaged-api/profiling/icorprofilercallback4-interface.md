---
title: "ICorProfilerCallback4 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4
helpviewer_keywords: ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efcbc9adce9b5cfc39c5eb3e1649a35d458e99c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4 인터페이스
공용 언어 런타임 (CLR) 사용 하 여 프로파일러에 정보를 통신 하는 콜백 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReJITParameters 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|새 다시 컴파일된 메서드 본문에 대 한 대체 코드 생성 플래그를 설정 하려면 코드 프로파일러를 허용 합니다.|  
|[MovedReferences2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고합니다.|  
|[ReJITCompilationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|적시에 (JIT) 컴파일러는 함수는 다시 컴파일은 되었음을 프로파일러에 알립니다.|  
|[ReJITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|적시에 (JIT) 컴파일러는 함수를 다시 시작 했습니다 프로파일러에 알립니다.|  
|[ReJITError 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|다시 컴파일한 요청을 처리 하는 동안 발생 한 오류를 보고 합니다.|  
|[SurvivingReferences2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|비압축 가비지 컬렉션의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
