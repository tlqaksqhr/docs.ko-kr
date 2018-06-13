---
title: ICorProfilerInfo3::GetAppDomainsContainingModule 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0d560b81aca1c6d859000cda682ee6c75fd7acb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454184"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a>ICorProfilerInfo3::GetAppDomainsContainingModule 메서드
지정된 모듈이 로드된 응용 프로그램 도메인의 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 로드된 모듈의 ID입니다.  
  
 `cAppDomainIds`  
 [in] `appDomainIds` 배열의 크기입니다.  
  
 `pcAppDomainIds`  
 [out] 반환된 요소의 총수에 대한 포인터입니다.  
  
 `appDomainIds`  
 [out] 응용 프로그램 도메인 ID 값의 배열입니다.  
  
## <a name="remarks"></a>설명  
 메서드는 호출자 할당 버퍼를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerFunctionEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
