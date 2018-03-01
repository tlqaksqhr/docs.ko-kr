---
title: "ICorProfilerCallback4::ReJITError 메서드"
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
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError 메서드
적시에 (JIT) 컴파일러는 다시 컴파일 프로세스에 오류가 발생 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] `ModuleID` 에 있는 실패 한 재컴파일을 가져오려고 합니다.  
  
 `methodId`  
 [in] `MethodDef` 메서드 다시 컴파일이 실패 한 시도 했습니다.  
  
 `functionId`  
 [in] 에 대 한 표시 되거나 다시 컴파일된 다시 컴파일 중인 함수 인스턴스. 이 값이 경우도 `NULL` (예를 들어 프로파일러가 지정 된 경우 다시 컴파일하지 않아도 메서드에 대 한 잘못 된 메타 데이터 토큰)를 인스턴스화 별으로 대신 메서드별로에 오류가 발생 하는 경우.  
  
 `hrStatus`  
 [in] 실패의 특징을 나타내는 HRESULT입니다. 값 목록에 대 한 상태 HRESULT 섹션을 참조 하십시오.  
  
## <a name="return-value"></a>반환 값  
 이 콜백의 반환 값은 무시됩니다.  
  
## <a name="status-hresults"></a>상태 HRESULTS  
  
|상태 배열 HRESULT|설명|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID` 또는 `methodDef` 토큰은 `NULL`합니다.|  
|CORPROF_E_DATAINCOMPLETE|모듈은 아직 완전히 로드되지 않았거나 언로드되는 중입니다.|  
|CORPROF_E_MODULE_IS_DYNAMIC|지정된 된 모듈은 동적으로 생성 됩니다 (예를 들어 여 `Reflection.Emit`),이 메서드에 의해 따라서 지원 되지 않습니다.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|메서드는 수집 가능한 어셈블리에 인스턴스화되고 따라서 수 없으면 다시 컴파일되지 않아도 됩니다. 형식 및 비 리플렉션 컨텍스트에 정의 된 함수 (예를 들어 `List<MyCollectibleStruct>`) 수집 가능한 어셈블리를 인스턴스화할 수 있습니다.|  
|E_OUTOFMEMORY|CLR은 JIT 다시 컴파일을 위해 지정 된 메서드를 표시 하는 동안 메모리 부족 합니다.|  
|기타|운영 체제가 CLR의 제어 범위를 벗어난 오류를 반환했습니다. 예를 들어 메모리의 페이지 액세스 보호를 변경 하려면 시스템 호출이 실패 하면 운영 체제 오류가 표시 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
