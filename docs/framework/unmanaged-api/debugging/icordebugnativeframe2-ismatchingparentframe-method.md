---
title: "ICorDebugNativeFrame2::IsMatchingParentFrame 메서드"
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
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc2d8eacb05e861290ad19a34c261943dc2959a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>ICorDebugNativeFrame2::IsMatchingParentFrame 메서드
지정된 된 프레임의 현재 프레임 부모 인지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pPotentialParentFrame`  
 [in] 부모 상태에 대 한 평가 하려는 frame 개체에 대 한 포인터입니다.  
  
 `pIsParent`  
 [out] `true` 경우 `pPotentialParentFrame` 현재 프레임의 부모인, 그렇지 않으면 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|부모 상태 반환 되었습니다.|  
|E_FAIL|부모 상태를 반환할 수 없습니다.|  
|E_INVALIDARG|`pPotentialParentFrame` 또는 `pIsParent`이 null입니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 `IsMatchingParentFrame`반환 `true` 프레임 개체를 메서드에 전달 메서드가 호출 된 프레임 개체의 부모인 경우. 지정된 된 프레임의 자식이 아닌 프레임에서 메서드를 호출 하는 경우 오류가 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugNativeFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
