---
title: "ICorProfilerCallback::ModuleLoadFinished 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished 메서드
모듈 로드 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 로드가 완료 된 모듈의 ID입니다.  
  
 `hrStatus`  
 [in] 모듈이 성공적으로 로드 되 고 있는지 여부를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 값 `moduleId` 될 때까지 정보 요청에 유효 하지는 `ModuleLoadFinished` 메서드를 호출 합니다.  
  
 일부 모듈 로드 후 계속 사용할 수는 `ModuleLoadFinished` 콜백 합니다. 실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다. 그러나 성공 HRESULT에서 `hrStatus` 로드 된 모듈의 첫 번째 부분 성공 했다는 것만 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ModuleLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
