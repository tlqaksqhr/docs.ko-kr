---
title: "ICorDebug::CanLaunchOrAttach 메서드"
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
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach 메서드
새 프로세스를 시작 하거나 지정한 기존 프로세스에 연결 하는 현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 가능한 지 여부를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwProcessId`  
 [in] 기존 프로세스의 ID입니다.  
  
 `win32DebuggingEnabled`  
 [in] 전달 `true` Win32 설정 된 상태로 실행 하려면 하거나 Win32 디버깅 그렇지 않으면 연결에 전달 하는 경우 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 현재 컴퓨터 및 런타임 구성에 대 한 정보를 제공 합니다. 새 프로세스를 시작 하거나 지정된 된 프로세스에 연결 하는 디버깅 서비스 결정 하면 s_ok이 고가 가능 합니다. 가능한 HRESULT 값은 같습니다.  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>설명  
 이 방법은 정보로 합니다. 인터페이스는 나타나도에서 시작 하는에서 반환 된 값에 상관 없이 프로세스에 연결 하거나 `CanLaunchOrAttach`합니다.  
  
 Win32 설정 된 상태로 시작 또는 Win32 디버깅 하도록 설정한 연결을 전달 하려는 경우 `true` 에 대 한 `win32DebuggingEnabled`합니다. 반환 된 HRESULT `CanLaunchOrAttach` 이 옵션을 사용 하는 경우 다를 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
