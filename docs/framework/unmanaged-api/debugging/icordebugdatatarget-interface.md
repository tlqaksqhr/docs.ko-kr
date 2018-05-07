---
title: ICorDebugDataTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 972c650e0fb3b42e943838b72faf2658f65543ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget 인터페이스
특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPlatform 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|프로세서 아키텍처와 대상 프로세스가 실행 되는 운영 체제를 포함 하는 플랫폼에 대 한 정보를 제공 합니다.|  
|[ReadVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|지정된 된 주소에서 시작 하는 인접 한 메모리 블록을 가져오고 제공된 된 버퍼에 반환 합니다.|  
|[GetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|지정된 된 스레드에 대 한 현재 스레드 컨텍스트를 요청합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugDataTarget` 및 해당 메서드는 다음과 같은 특징이 있습니다.  
  
-   디버깅 서비스의 메모리와 대상 프로세스의 다른 데이터를 액세스 하려면이 인터페이스에서 메서드를 호출 합니다.  
  
-   디버거 클라이언트 (예를 들어 활성 프로세스 또는 메모리 덤프) 특정 대상에 따라이 인터페이스를 구현 해야 합니다.  
  
-   `ICorDebugDataTarget` 또 다른 구현 된 메서드 내 에서만 메서드를 호출할 수 있습니다 `ICorDebug*` 인터페이스입니다. 이렇게 하면 디버거 클라이언트에 특정 스레드에서 호출 시기를 제어 합니다.  
  
-   `ICorDebugDataTarget` 구현 항상 대상에 대 한 최신 정보를 반환 해야 합니다.  
  
 대상 프로세스를 중지 하는 동안 어떤 식으로든에서 변경 되지 `ICorDebug*` 인터페이스 (및 따라서 `ICorDebugDataTarget` 메서드) 호출 합니다. 대상이 활성 프로세스 및 해당 상태의 변경 내용을 인 경우는 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드가 대체 ICorDebugProcess 인스턴스를 제공 하기 위해 다시 호출 수입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
