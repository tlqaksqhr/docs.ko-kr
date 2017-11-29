---
title: "ICorDebugModule::EnableClassLoadCallbacks 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableClassLoadCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9045cceda54e6fe89c8c1baa8d4b9fa63105607
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks 메서드
컨트롤 여부는 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 이 모듈에 대 한 콜백을 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bClassLoadCallbacks`  
 [in] 이 값을 설정 `true` 공용 언어 런타임 (CLR) 호출을 사용 하 여 `ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 관련된 이벤트가 발생할 때 메서드.  
  
 기본값은 `false` 동적이 지 않은 모듈에 대 한 합니다. 값은 항상 `true` 동적 모듈에 대 한 변경할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 `ICorDebugManagedCallback::LoadClass` 및 `ICorDebugManagedCallback::UnloadClass` 콜백을 동적 모듈의 항상 사용 하도록 설정 하 고 비활성화할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 
