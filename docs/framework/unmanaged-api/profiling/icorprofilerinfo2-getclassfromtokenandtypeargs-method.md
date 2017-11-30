---
title: "ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 332be5616ac11fc89df8c8d54aa5c0cbc49491ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드
가져옵니다는 `ClassID` 지정한 메타 데이터 토큰을 사용 하 여 형식의 및 `ClassID` 값 형식 인수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] 형식 프로시저가 모듈의 ID입니다.  
  
 `typeDef`  
 [in] `mdTypeDef` 유형을 참조 하는 메타 데이터 토큰입니다.  
  
 `cTypeArgs`  
 [in] 지정된 된 형식에 대 한 형식 매개 변수 수를 지정 합니다. 이 값에는 제네릭이 아닌 형식에는 0 이어야 합니다.  
  
 `typeArgs`  
 [in] 배열 `ClassID` 값을 각각는 인수 형식입니다. 값 `typeArgs` 경우 NULL이 될 수 `cTypeArgs` 0으로 설정 됩니다.  
  
 `pClassID`  
 [out] 에 대 한 포인터는 `ClassID` 지정 된 형식의 합니다.  
  
## <a name="remarks"></a>설명  
 호출의 `GetClassFromTokenAndTypeArgs` 메서드는 `mdTypeRef` 대신는 `mdTypeDef` 메타 데이터 토큰 예기치 않은 결과 가질 수 있습니다; 호출자가 해결 해야는 `mdTypeRef` 에 `mdTypeDef` 전달할 경우.  
  
 형식을 아직 로드 되지 않은 경우 호출 `GetClassFromTokenAndTypeArgs` 로드를 여러 컨텍스트에서 위험한 작업을 트리거합니다. 예를 들어, 런타임에서 순환 로드를 시도할 때 모듈이 나 다른 형식을 로드 하는 동안이 메서드를 호출 무한 루프가 발생할 수입니다.  
  
 일반적으로 사용 하 여 `GetClassFromTokenAndTypeArgs` 않는 것이 좋습니다. 저장 해야 프로파일러 특정 형식에 대 한 이벤트에 관심이 `ModuleID` 및 `mdTypeDef` 해당 형식 및 사용 하 여 [icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) 확인 하려면 여부는 지정 된 `ClassID` 의입니다는 필요한 형식입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
