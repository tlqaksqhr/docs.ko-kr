---
title: ICorProfilerInfo4::GetReJITIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1055366576f45a7ca137b6d8170d1786c2ba4492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs 메서드
모든 JIT 다시 컴파일된 버전의 지정된 된 함수 여전히 할당 되는 식별 하는 Id의 배열을 반환 합니다. 여기에 이후에 되돌릴 되었지만 아직 사용할 수 없는 (예를 들어 되돌려 진된 함수를 포함 하는 응용 프로그램 도메인 사용 중인 경우 여전히) 함수의 JIT 다시 컴파일된 버전 포함 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] `FunctionID` 를 열거할 버전에 대 한 함수 인스턴스.  
  
 `cReJitIds`  
 [in] JIT 다시 컴파일된 Id에 할당 된 수의 `reJitIds` 배열입니다.  
  
 `pcReJitIds`  
 [out] JIT 다시 컴파일된 Id의 실제 수입니다.  
  
 `reJitIds`  
 [out] 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자에 게 할당 된 배열입니다.  
  
## <a name="remarks"></a>설명  
 `GetReJITIDs` 지정 된 함수 인스턴스에 대 한 활성 JIT 다시 컴파일된 Id를 열거합니다. 다른 동일한 사용 패턴을 따르는 `ICorProfilerInfo` 호출자 할당 버퍼를 허용 하는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
