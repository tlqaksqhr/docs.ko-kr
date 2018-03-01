---
title: "ICorDebugManagedCallback::UpdateModuleSymbols 메서드"
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
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad5a84268f3810a1fb73a21a6bd8106e82ccbd78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a>ICorDebugManagedCallback::UpdateModuleSymbols 메서드
공용 언어 런타임 모듈에 대 한 기호 변경 되었다는 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAppDomain`  
 [in] 기호 변경 되었습니다 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pModule`  
 [in] 모듈의 기호가 변경 되었음을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.  
  
 `pSymbolStream`  
 [in] Win32 COM에 대 한 포인터 `IStream` 수정 된 기호를 포함 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 하 여 모듈의 기호의 디버거 뷰를 업데이트할 수 있게 [isymunmanagedreader:: Updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 또는 [isymunmanagedreader:: Replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)합니다.  
  
 이 콜백은 같은 모듈에 대 한 여러 번 발생할 수 있습니다.  
  
 디버거는 바인딩되지 않은 소스 수준 중단점을 바인딩할 시도해 보십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
