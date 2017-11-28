---
title: "ICorDebugDataTarget3::GetLoadedModules 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>ICorDebugDataTarget3::GetLoadedModules 메서드
지금까지 로드된 모듈 목록을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cRequestedModules`  
 [in] 정보가 요청된 모듈 수입니다.  
  
 `pcFetchedModules`  
 [out] 정보가 반환된 모듈 수에 대한 포인터입니다.  
  
 `pLoadedModules`  
 [out] 배열에 대 한 포인터 [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugDataTarget3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
