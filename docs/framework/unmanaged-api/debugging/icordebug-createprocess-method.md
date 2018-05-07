---
title: ICorDebug::CreateProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 044f94a567dc4bc2b169ba2a5f2a5d7b4f98e516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess 메서드
프로세스와 디버거 제어 기본 스레드를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lpApplicationName`  
 [in] 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 모듈 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.  
  
 `lpCommandLine`  
 [in] 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 응용 프로그램 이름 (예: "SomeApp.exe") 첫 번째 인수로 사용 해야 합니다.  
  
 `lpProcessAttributes`  
 [in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스에 대 한 보안 설명자를 지정 하는 구조입니다. 경우 `lpProcessAttributes` 가 null 인 프로세스 기본 보안 설명자를 가져옵니다.  
  
 `lpThreadAttributes`  
 [in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스의 주 스레드에 대 한 보안 설명자를 지정 하는 구조입니다. 경우 `lpThreadAttributes` 가 null 인 스레드가 기본 보안 설명자를 가져옵니다.  
  
 `bInheritHandles`  
 [in] 로 설정 `true` 시작된 프로세스에 의해 상속 가능한 각 핸들 호출 프로세스에이 상속 됨을 나타내기 위해 또는 `false` 핸들이 상속 되지 않습니다 나타냅니다. 상속 된 핸들에는 원래 핸들와 동일한 값 및 액세스 권한을 가져야 합니다.  
  
 `dwCreationFlags`  
 [in] 비트 조합 된 [Win32 프로세스 생성 플래그가](http://go.microsoft.com/fwlink/?linkid=69981) 우선 순위 클래스 및 시작 된 프로세스의 동작을 제어 하 합니다.  
  
 `lpEnvironment`  
 [in] 새로운 프로세스에 대 한 환경 블록에 대 한 포인터입니다.  
  
 `lpCurrentDirectory`  
 [in] 프로세스에 대 한 현재 디렉터리에 전체 경로 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 null 이면 새 프로세스에 호출 프로세스와 현재 동일한 드라이브와 디렉터리 제공 됩니다.  
  
 `lpStartupInfo`  
 [in] Win32에 대 한 포인터 `STARTUPINFOW` 창 스테이션, 바탕 화면, 표준 핸들 및 시작 된 프로세스에 대 한 주 창의 모양을 지정 하는 구조입니다.  
  
 `lpProcessInformation`  
 [in] Win32에 대 한 포인터 `PROCESS_INFORMATION` 시작 프로세스에 대 한 식별 정보를 지정 하는 구조입니다.  
  
 `debuggingFlags`  
 [in] 디버깅 옵션을 지정 하는 CorDebugCreateProcessFlags 열거형의 값입니다.  
  
 `ppProcess`  
 [out] 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드의 매개 변수는 Win32의와 동일 `CreateProcess` 메서드.  
  
 관리 되지 않는 혼합 모드 디버깅을 사용 하려면 설정 `dwCreationFlags` DEBUG_PROCESS를 &#124; DEBUG_ONLY_THIS_PROCESS 합니다. 관리 되는 디버깅만 사용 하려는 경우에 이러한 플래그를 설정 하지 마십시오.  
  
 디버거 및 프로세스를 디버깅 (연결 된 프로세스) 하는 경우 단일 콘솔을 공유 하 고 콘솔 잠금을 유지 하 고 디버그 이벤트에서 중지 하는 연결 된 프로세스에 대 한 가능한는 interop 디버깅을 사용 합니다. 디버거는 콘솔을 사용 하려는 모든 시도가 차단 다음 합니다. 이 문제를 방지 하려면에서 CREATE_NEW_CONSOLE 플래그를 설정의 `dwCreationFlags` 매개 변수입니다.  
  
 Interop 디버깅 IA 64 기반 및 AMD64 기반 플랫폼에서와 같은 Win9x 및 비 x86 플랫폼에서 지원 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
