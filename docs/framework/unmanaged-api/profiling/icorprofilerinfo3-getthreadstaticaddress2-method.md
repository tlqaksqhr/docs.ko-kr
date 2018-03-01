---
title: "ICorProfilerInfo3::GetThreadStaticAddress2 메서드"
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
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 136b68f886899430dbfc672b8e3e534d093bc617
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>ICorProfilerInfo3::GetThreadStaticAddress2 메서드
지정된 스레드 및 응용 프로그램 도메인의 범위에 있는 지정된 Thread 정적 필드의 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classId`  
 [in] 요청 된 thread 정적 필드를 포함 하는 클래스의 ID입니다.  
  
 `fieldToken`  
 [in] 요청 된 thread 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `appDomainId`  
 [in] 응용 프로그램 도메인의 ID입니다.  
  
 `threadId`  
 [in] 요청 된 정적 필드에 대 한 범위를 한 스레드의 ID입니다.  
  
 `ppAddress`  
 [out] 지정 된 스레드 내에 있는 정적 필드의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetThreadStaticAddress2` 메서드에서 다음 중 하나를 반환할 수 있습니다.  
  
-   지정된 된 정적 필드의 주소 지정된 된 컨텍스트에서 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.  
  
-   가비지 수집 힙에서 있을 수 있는 개체의 주소입니다. 이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 수집 후 잘못 될 수 있습니다.  
  
 클래스의 클래스 생성자 완료 되기 전에 `GetThreadStaticAddress2` 정적 필드 중 일부를 초기화할 수 있습니다는 이미 있지만 CORPROF_E_DATAINCOMPLETE 정적의 모든 필드에 반환 하 고 가비지 수집 개체 루 팅입니다.  
  
 [icorprofilerinfo2:: Getthreadstaticaddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) 메서드는 비슷합니다는 `GetThreadStaticAddress2` 메서드를 하지만 응용 프로그램 도메인 인수를 허용 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
