---
title: "ICorProfilerObjectEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfeec7c3ee2038b77549e53b10534d817b667687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumnext-method"></a>ICorProfilerObjectEnum::Next 메서드
시퀀스에서 열거자의 현재 위치부터 시작 하는 개체의 순차적인 컬렉션에서 지정 된 개수의 연속 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 개체 수입니다.  
  
 `objects`  
 [out] 배열 `ObjectID` 각각 검색 된 개체를 나타내는 값입니다.  
  
 `pceltFetched`  
 [out] `objects` 배열에 실제로 반환된 모듈 수에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerObjectEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
