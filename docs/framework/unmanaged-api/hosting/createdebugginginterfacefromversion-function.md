---
title: "CreateDebuggingInterfaceFromVersion 함수"
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
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3f269f5b1758481995d6064e7137e62bff4a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion 함수
만듭니다는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 지정된 된 버전 정보에 따라 개체입니다.  
  
 이 함수에서 사용 되지 않는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 대신, 사용 공용 언어 런타임 (CLR) 2.0에 대 한 인터페이스를 가져올 수는 [iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 메서드 CLSID_CLRDebuggingLegacy 클래스 식별자 및 IID_ICorDebug 인터페이스 식별자를 지정 합니다. CLR 4에 대 한 인터페이스를 가져오거나 이상 버전에서는 호출 하 여 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수 및 클래스 식별자 CLSID_CLRDebugging IID_ICLRDebugging 인터페이스 식별자를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iDebuggerVersion`  
 [in] 버전의 `ICorDebug` 디버거를 통해 사용할 수 있는 합니다. 참조는 [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) 유효한 값에 대 한 열거형입니다.  
  
 `szDebuggeeVersion`  
 [in] 응용 프로그램이 나 프로세스를 디버깅할와 연결 된 공용 언어 런타임 버전입니다. 참조는 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) 또는 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) 이 값을 검색에 대 한 내용은 메서드.  
  
 `ppCordb`  
 [out] 에 대 한 포인터를 받는 위치는 `ICorDebug` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h 파일에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szDebuggeeVersion`또는 `ppCordb` null 또는 버전 문자열이 잘못 되었습니다.|  
  
## <a name="remarks"></a>설명  
 `szDebuggeeVersion` 매개 변수 MSCorDbi.dll의 해당 버전에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
