---
title: ICorDebugDataTarget::GetPlatform 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ae761b2d48552aded8191ddbea26552d8da277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411020"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform 메서드
프로세서 아키텍처와 대상 프로세스가 실행 되는 운영 체제를 포함 하는 플랫폼에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pTargetPlatform`  
 [out] 에 대 한 포인터는 [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) 대상 플랫폼에 설명 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 `CorDebugPlatformEnum` 열거형 반환 값은 사용 하 여는 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스 포인터 크기, 주소 공간 레이아웃, 레지스터 집합, 명령 형식, 컨텍스트 레이아웃 등과 같은 대상 프로세스의 세부 정보를 확인 하 고 호출 규칙입니다.  
  
 `pTargetPlatform` 값 사용 중인 실제 하드웨어를 지정 하는 대신 대상에 대 한 에뮬레이트 되는 플랫폼을 참조할 수 있습니다. 예를 들어 Windows 운영 체제의 64 비트 버전의 Windows on Windows (WOW) 환경에서에서 실행 되는 프로세스를 사용할지는 `CORDB_PLATFORM_WINDOWS_X86` 의 값은 [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) 열거 합니다.  
  
 이 메서드는 성공 해야 합니다. 실패 한 경우 대상 플랫폼은 사용할 수 없습니다. 메서드는 다음과 같은 이유로 실패할 수 있습니다.  
  
-   대상에 대해 에뮬레이트 되는 플랫폼은 사용할 수 없습니다.  
  
-   대상 플랫폼에 실제 하드웨어에서 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
