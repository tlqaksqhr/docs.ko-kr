---
title: "ICorProfilerCallback::JITInlining 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining 메서드
Time (JIT) 컴파일러 다른 함수와 같은 줄 함수 삽입를 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `callerId`  
 [in] 함수의 ID는 `calleeId` 함수 삽입 됩니다.  
  
 `calleeId`  
 [in] 삽입 될 함수의 ID입니다.  
  
 `pfShouldInline`  
 [out] `true` ; 되려면 삽입을 허용 하 고, 그러지 `false`합니다.  
  
## <a name="remarks"></a>설명  
 프로파일러 설정할 수 `pfShouldInline` 를 `false` 방지 하기 위해는 `calleeId` 에 삽입 되지 함수는 `callerId` 함수입니다. 또한 프로파일러 전체적으로 비활성화할 수 인라인 삽입 COR_PRF_DISABLE_INLINING 값을 사용 하 여는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거 합니다.  
  
 삽입 하는 함수를 인라인으로 시작 또는 종료에 대 한 이벤트 발생 하지 않습니다. 따라서 프로파일러 설정 해야 `pfShouldInline` 를 `false` 정확한 호출 그래프를 생성 하기 위해. 설정 `pfShouldInline` 를 `false` 인라인 삽입 일반적으로 속도 높이고 및 삽입 된 메서드에 대 한 별도 JIT 컴파일 이벤트의 수를 줄일 수 때문에 성능에 영향을 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
