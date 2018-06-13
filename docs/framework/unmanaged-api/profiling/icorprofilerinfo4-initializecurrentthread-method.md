---
title: ICorProfilerInfo4::InitializeCurrentThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5a4a6bc7b1e79068b11b099352cec64dd09f301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459455"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread 메서드
후속 프로파일러 API 해당 교착 상태를 방지할 수 있도록 동일한 스레드에서 호출 되기 전에 현재 스레드를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>설명  
 호출 하는 것이 좋습니다 `InitializeCurrentThread` API 있지만 프로파일러를 호출 하는 모든 스레드에서 스레드를 일시 중단 합니다. 이 메서드는 일반적으로 샘플링 프로파일러를 호출할 자신의 스레드를 만들는가 사용 되는 [icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 대상 스레드가 일시 중단 된 동안 메서드 스택을 안내 합니다. 호출 하 여 `InitializeCurrentThread` 프로파일러 처음 만들 때 샘플링 스레드, 프로파일러 첫 번째 호출 하는 동안 CLR을 수행 하는 스레드 지연 초기화 확인 수 `DoStackSnapshot` 이제 단어란 안전 하 게 다른 스레드가 없는 경우 일시 중지 됩니다.  
  
> [!NOTE]
>  `InitializeCurrentThread` 잠금 하 고 교착 상태가 발생할 수 있는 작업을 완료 하는 데 미리 초기화를 수행 합니다. 호출 `InitializeCurrentThread` 일시 중단 된 스레드가 없는 경우에 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
