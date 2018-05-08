---
title: ICorProfilerInfo2::GetContextStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d787e3eae59218c46a95c327a0f93502c3833d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress 메서드
지정된 된 컨텍스트 범위 내에 있는 지정된 된 컨텍스트 정적 필드에 대 한 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classId`  
 [in] 요청한 컨텍스트 정적 필드를 포함 하는 클래스의 ID입니다.  
  
 `fieldToken`  
 [in] 요청한 컨텍스트 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `contextId`  
 [in] 요청한 컨텍스트 정적 필드에 대 한 범위 컨텍스트의 ID입니다.  
  
 `ppAddress`  
 [out] 지정된 된 컨텍스트 내에 있는 정적 필드의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetContextStaticAddress` 메서드에서 다음 중 하나를 반환할 수 있습니다.  
  
-   지정된 된 정적 필드의 주소 지정된 된 컨텍스트에서 할당 되지 않은 경우 CORPROF_E_DATAINCOMPLETE HRESULT입니다.  
  
-   가비지 수집 힙에서 있을 수 있는 개체의 주소입니다. 이러한 주소 가비지 수집 후 프로파일러 가정 하지 않아야 유효한 지 하므로 가비지 수집 후 잘못 될 수 있습니다.  
  
 클래스의 클래스 생성자 완료 되기 전에 `GetContextStaticAddress` 정적 필드 중 일부를 초기화할 수 있습니다는 이미 있지만 CORPROF_E_DATAINCOMPLETE 정적의 모든 필드에 반환 하 고 가비지 수집 개체 루 팅입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
