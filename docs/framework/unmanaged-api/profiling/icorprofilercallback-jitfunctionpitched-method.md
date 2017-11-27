---
title: "ICorProfilerCallback::JITFunctionPitched 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5b14bc5735c83897e818ca2038455e0c6510e27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched 메서드
프로파일러에 알립니다 하는 시간 (JIT) 된 함수-컴파일된 메모리에서 제거 되었습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 제거 된 함수 ID입니다.  
  
## <a name="remarks"></a>설명  
 제거 된 함수가 호출 되는 경우 프로파일러 함수를 다시 컴파일할 때 새 JIT 컴파일 이벤트를 받게 됩니다. 현재, 공용 언어 런타임 (CLR) JIT 컴파일러가 함수를 제거 하지 메모리에서이 콜백은 현재 사용 하지 않는 고 프로파일러에서 수신 되지 않습니다.  
  
 값 `functionId` 함수를 다시 컴파일할 때까지 유효 하지 않습니다. 함수를 다시 컴파일할 때 동일한 `functionId` 값이 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
