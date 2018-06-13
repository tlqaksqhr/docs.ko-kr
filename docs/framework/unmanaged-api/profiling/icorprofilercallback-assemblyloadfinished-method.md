---
title: ICorProfilerCallback::AssemblyLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f000b6e944be7bd2e38f97e40176952cb19605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450634"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished 메서드
어셈블리 로드 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `assemblyId`  
 [in] 로드 된 어셈블리를 식별 합니다.  
  
 `hrStatus`  
 [in] 어셈블리 로드를 성공적으로 완료할 지 여부를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 값 `assemblyId` 될 때까지 정보 요청에 유효 하지는 `AssemblyLoadFinished` 메서드를 호출 합니다.  
  
 일부 요소는 어셈블리를 로드 한 후 계속 사용할 수는 `AssemblyLoadFinished` 콜백 합니다. 실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다. 그러나 성공 HRESULT에서 `hrStatus` 어셈블리 로드의 첫 번째 부분 성공 했다는 것만 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
