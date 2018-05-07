---
title: ICorDebugEval::NewArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray 메서드
지정한 요소 형식 및 차원에 대 한 새 배열을 할당합니다.  
  
 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [icordebugeval2:: Newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `elementType`  
 [in] 배열의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다.  
  
 `pElementClass`  
 [in] 요소 클래스를 지정 하는 ICorDebugClass 개체에 대 한 포인터입니다. 이 값은 요소 형식은 기본 형식인 경우에 null 일 수 있습니다.  
  
 `rank`  
 [in] 배열의 차원 수입니다. .NET Framework 2.0에서이 값에는 1 이어야 합니다.  
  
 `dims`  
 [in] 바이트 배열의 각 차원 크기입니다.  
  
 `lowBounds`  
 [in] 선택적 항목으로, 배열의 각 차원 하 한입니다. 이 값을 생략 하면 각 차원에 대 한 하한값 0으로 가정 합니다.  
  
## <a name="remarks"></a>설명  
 배열의는 스레드가 현재 실행 중인 응용 프로그램 도메인에서 항상 만들어집니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1
