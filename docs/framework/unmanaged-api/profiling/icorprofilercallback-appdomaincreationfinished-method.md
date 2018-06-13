---
title: ICorProfilerCallback::AppDomainCreationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0017cff43f7a1b1bdd90806f50abb374a96dadf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450426"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished 메서드
응용 프로그램 도메인을 이미 만들었다고 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `appDomainId`  
 [in] 작성 된 도메인을 식별 합니다.  
  
 `hrStatus`  
 [in] 응용 프로그램 도메인을 만드는 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 응용 프로그램 ID가 될 때까지 정보 요청에 잘못 된 `AppDomainCreationFinished` 메서드를 호출 합니다.  
  
 일부 응용 프로그램 도메인을 로드 한 후 계속 사용할 수는 `AppDomainCreationFinished` 콜백 합니다. 실패 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다. 그러나 성공 HRESULT에서 `hrStatus` 응용 프로그램 도메인을 만드는 첫 번째 단계는 성공 했다는 것만 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
