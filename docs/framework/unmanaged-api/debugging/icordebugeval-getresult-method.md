---
title: ICorDebugEval::GetResult 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413061"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult 메서드
이 평가의 결과를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppResult`  
 [out] 확인이 정상적으로 완료 하는 경우이 평가의 결과 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetResult` 메서드는 평가 완료 한 후에 유효 합니다.  
  
 확인이 정상적으로 완료 하는 경우 `ppResult` 결과 지정 합니다. 예외와 함께 종료 하는 결과 throw 된 예외입니다. 새 개체에 대 한 평가 경우 결과 새 개체에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
