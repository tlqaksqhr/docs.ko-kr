---
title: "ICorDebugProcess5::EnumerateGCReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44975a7896c71ce8061dedde13d31c4fbb88d6a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences 메서드
프로세스의 가비지 수집 하는 모든 개체에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `enumerateWeakReferences`  
 [in] 약한 참조를 열거도 지 여부를 나타내는 부울 값입니다. 경우 `enumerateWeakReferences` 은 `true`, `ppEnum` 열거자는 강력한 참조 및 약한 참조를 모두 포함 합니다. 경우 `enumerateWeakReferences` 은 `false`, 열거자는 강력한 참조만 포함 합니다.  
  
 `ppEnum`  
 [out] 주소에 대 한 포인터는 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) 즉 하는 열거자 개체에 대 한 가비지 수집 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로세스에서 관리 되는 개체에 대 한 전체 루 팅 체인을 결정 하는 방법을 제공 하며 개체가 아직 활성화 된 이유를 확인 하기 위해 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess5 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
