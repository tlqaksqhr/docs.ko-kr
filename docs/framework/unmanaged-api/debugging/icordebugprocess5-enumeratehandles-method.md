---
title: "ICorDebugProcess5::EnumerateHandles 메서드"
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
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9bf9f1a4d565e0af4f3ee34a2805116407027d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles 메서드
프로세스에서 개체 핸들에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `types`  
 [in] 비트 조합 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 컬렉션에 포함할에 대 한 핸들의 형식을 지정 하는 값입니다.  
  
 `ppENum`  
 [out] 주소에 대 한 포인터는 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 즉 하는 열거자 개체에 대 한 가비지 수집 합니다.  
  
## <a name="remarks"></a>설명  
 `EnumerateHandles`핸들 테이블의 검사를 지 원하는 도우미 함수가입니다. 비슷합니다는 [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) 메서드와 비슷하지만 대신 채우기는 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 가비지 수집 된 모든 개체를 사용 하 여 컬렉션 것 핸들 테이블의 핸들이 있는 개체에 대해서만 포함 됩니다.  
  
 `types` 매개 변수 컬렉션에 포함할 핸들 유형을 지정 합니다. `types`다음 세 가지 멤버 중 하나일 수 있습니다는 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 열거:  
  
-   `CorHandleStrongOnly`(핸들 강력한 참조에만 해당)입니다.  
  
-   `CorHandleWeakOnly`(핸들 약한 참조에만 해당)입니다.  
  
-   `CorHandleAll`(모든 핸들)입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
