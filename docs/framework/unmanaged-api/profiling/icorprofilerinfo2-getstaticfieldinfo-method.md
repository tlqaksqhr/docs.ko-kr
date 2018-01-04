---
title: "ICorProfilerInfo2::GetStaticFieldInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a13a07aeb90d7ad05ca83bf273fe999b9a81bd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo 메서드
지정된 된 필드에 적용 되는 정적의 종류를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classId`  
 [in] 정적 필드 정의 된 클래스의 ID입니다.  
  
 `fieldToken`  
 [in] 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `pFieldInfo`  
 [out] 값에 대 한 포인터는 [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) 경우, 정적의 종류에 적용 되는 필드 및 지정 된 필드가 정적 인지 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 정적 필드의 주소를 얻기 위해 호출할 함수를 확인 하려면이 정보를 사용할 수 있습니다.  
  
 프로파일러 코드는 정적 필드의 주소에 실제로 있는지 확인 하는 메타 데이터를 확인 해야 합니다. 정적 리터럴 (즉, 상수) 메타 데이터에만 존재 하 고 주소를가지고 있지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
