---
title: "ICorDebugThread3::GetActiveInternalFrames 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ecfbaeff9416ee8e6541a23bac6ec76f99abd2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames 메서드
내부 프레임의 배열을 반환 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체)를 스택에 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cInternalFrames`  
 [in] 예상 하는 내부 프레임 수가 `ppInternalFrames`합니다.  
  
 `pcInternalFrames`  
 [out] 에 대 한 포인터는 `ULONG32` 내부 스택 프레임의 수가 포함 된 합니다.  
  
 `ppInternalFrames`  
 [out에서] 내부 스택 프레임의 배열의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) 개체가 성공적으로 만들어졌습니다.|  
|E_INVALIDARG|`cInternalFrames`0이 아닌 및 `ppInternalFrames` 은 `null`, 또는 `pcInternalFrames` 은 `null`합니다.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`내부 프레임의 개수 보다 작습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 내부 프레임은 임시 데이터를 저장 하려면 런타임에 의해 스택에 밀어 넣은 데이터 구조입니다.  
  
 처음 호출할 때는 `GetActiveInternalFrames`를 설정 해야는 `cInternalFrames` 매개 변수를 0 (영) 및 `ppInternalFrames` 매개 변수를 null입니다. 때 `GetActiveInternalFrames` 먼저 반환 `pcInternalFrames` 스택에 내부 프레임 수를 포함 합니다.  
  
 `GetActiveInternalFrames`다음 해야를 두 번 호출할 수 있습니다. 적절 한 수를 전달 해야 (`pcInternalFrames`)에 `cInternalFrames` 매개 변수를 적절 한 크기의 배열에 대 한 포인터를 지정 하 고 `ppInternalFrames`합니다.  
  
 사용 하 여는 [icordebugstackwalk:: Getframe](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) 실제 반환 하는 메서드 스택 프레임입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
