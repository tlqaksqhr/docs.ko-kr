---
title: ICorProfilerCallback::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd53d74dfe8199617df47e46641b71203abf6e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize 메서드
새 공용 언어 런타임 (CLR) 응용 프로그램 시작 될 때마다 코드 프로파일러를 초기화 하기 위해 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pICorProfilerInfoUnk`  
 [에](/cpp/atl/iunknown) 프로파일러에 대해 쿼리해야 하는 인터페이스는 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 인터페이스 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `Initialize` 호출은 통해서만 변경할 수 없는 콜백을 사용 하도록 설정 (또는 사용 안 함)입니다. 콜백 하 여 활성화 되 면는 `Initialize` 호출 하 고, 나중에 사용 하 여 해제할 수 없습니다 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)합니다. COR_PRF_MONITOR_IMMUTABLE 값은 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형은 변경할 수 없는 이벤트를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Shutdown 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
