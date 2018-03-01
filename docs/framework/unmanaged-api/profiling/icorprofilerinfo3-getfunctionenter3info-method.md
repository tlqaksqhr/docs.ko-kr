---
title: "ICorProfilerInfo3::GetFunctionEnter3Info 메서드"
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
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b7053f526d415dbaef872e37d139d25ae5ac462
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info 메서드
프로파일러에 보고 하는 함수의 스택 프레임 및 인수 정보를 제공는 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) 함수입니다. 이 함수는 `FunctionEnter3WithInfo` 콜백 중에만 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 입력 중인 함수의 `FunctionID`입니다.  
  
 `eltInfo`  
 [in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다. 동일한 프로파일러 제공 해야 `eltInfo` 로부터 받은입니다는 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) 함수 합니다.  
  
 `pFrameInfo`  
 [out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다. 이 핸들은 프로파일러가 `GetFunctionEnter3Info` 메서드를 호출한 `FunctionEnter3WithInfo` 콜백 중에만 유효합니다.  
  
 `pcbArgumentInfo`  
 [out에서] 총 크기 (바이트)에서에 대 한 포인터의는 [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 구조 (및 모든 추가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 에서가리키는인수범위에대한구조`pArgumentInfo`). 지정된 크기가 충분하지 않으면 ERROR_INSUFFICIENT_BUFFER가 반환되고 예상 크기가 `pcbArgumentInfo`에 저장됩니다. 단순히 `*pcbArgumentInfo`의 예상 값을 검색하기 위해 `GetFunctionEnter3Info`를 호출하려면 `*pcbArgumentInfo`=0 및 `pArgumentInfo`=NULL을 설정합니다.  
  
 `pArgumentInfo`  
 [out] 에 대 한 포인터는 [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 왼쪽에서 오른쪽 순서로 메모리에서 함수 인수의 위치를 설명 하는 구조입니다.  
  
## <a name="remarks"></a>설명  
 프로파일러는 검사되는 함수의 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조체에 대해 충분한 공간을 할당해야 하며 `pcbArgumentInfo` 매개 변수에 크기를 나타내야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
