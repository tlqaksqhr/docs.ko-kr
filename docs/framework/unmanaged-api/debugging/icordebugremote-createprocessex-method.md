---
title: "ICorDebugRemote::CreateProcessEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.CreateProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00709ffe4695ea0b56982cb60df15c2991b49d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx 메서드
디버거에서 원격 컴퓨터에서 프로세스를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRemoteTarget`  
 [in] 에 대 한 포인터는 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)합니다. 프로세스를 시작할 원격 컴퓨터를 결정 하는 데 사용 합니다.  
  
 `lpApplicationName`  
 [in] 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 모듈 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.  
  
 `lpCommandLine`  
 [in] 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `lpProcessAttributes`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `lpThreadAttributes`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `bInheritHandles`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `dwCreationFlags`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `lpEnvironment`  
 [in] 새로운 프로세스에 대 한 환경 블록에 대 한 포인터입니다.  
  
 `lpCurrentDirectory`  
 [in] 프로세스에 대 한 현재 디렉터리에 전체 경로 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 null 이면 새 프로세스에 호출 프로세스와 현재 동일한 드라이브와 디렉터리 제공 됩니다.  
  
 `lpStartupInfo`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `lpProcessInformation`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `debuggingFlags`  
 [in] 원격 디버깅을 위해 사용 되지 않습니다.  
  
 `ppProcess`  
 [out] 프로세스를 나타내는 "ICorDebugProcess 인터페이스" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 디버깅을 위해 원격 컴퓨터와 반환 된 "ICorDebugProcess 인터페이스" 프로세스를 제대로 시작 합니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 원격 컴퓨터에서 프로세스를 시작 하 고 디버깅을 위해 "ICorDebugProcess 인터페이스"를 반환할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 Silverlight에는 혼합 모드 디버깅이 지원 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRemote 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
