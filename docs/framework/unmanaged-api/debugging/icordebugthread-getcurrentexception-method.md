---
title: ICorDebugThread::GetCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82686fdd14783257987ec5bf9a24db7d87049d42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421748"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException 메서드
관리 코드에서 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppExceptionObject`  
 [out] 주소에 대 한 포인터는 `ICorDebugValue` 관리 코드에서 throw 되는 예외를 나타내는 개체입니다.  
  
## <a name="remarks"></a>설명  
 예외 개체는 예외가 끝날 때까지 시간부터 존재는 `catch` 블록입니다. ICorDebugEval 메서드에 의해 수행 되는 함수 실행 설정에서 예외 개체를 지우고 완료에서 복원 됩니다.  
  
 예외 (예를 들어 예외가 throw 되 면 필터 또는 함수 실행) 중첩 될 수 있으므로 단일 스레드로 여러 해결 되지 않은 예외가 있을 수 있습니다. `GetCurrentException` 가장 최근 예외를 반환합니다.  
  
 예외 개체와 형식 예외 기간 동안 변경 될 수 있습니다. 예를 들어 x 형식의 예외가 throw 되 면 공용 언어 런타임 (CLR) 될 수 있습니다 메모리가 부족 하 고 메모리 부족 예외로 승격 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
