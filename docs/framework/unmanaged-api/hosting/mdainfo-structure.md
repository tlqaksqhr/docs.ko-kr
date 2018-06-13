---
title: MDAInfo 구조체
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5164e85ecc97de99dcc493c2ba5efa8fc3468471
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443182"
---
# <a name="mdainfo-structure"></a>MDAInfo 구조체
에 대 한 세부 정보를 제공는 `Event_MDAFired` 관리 디버깅 도우미 (MDA) 만들기를 트리거하는 이벤트입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`lpMDACaption`|현재 MDA의 제목입니다. 오류를 발생 시킨의 종류를 설명 하는 제목은 `Event_MDAFired` 이벤트입니다.|  
|`lpMDAMessage`|현재 MDA에서 제공 되는 출력 메시지입니다.|  
  
## <a name="remarks"></a>설명  
 관리 디버깅 도우미 (Mda)은 런타임 실행 엔진에서 디버깅 하는 공용 언어 런타임 (CLR)를 식별 하는 등의 작업 수행과 함께에서 작동 하는 도우미 또는 상태에 대 한 추가 정보를 덤프는 엔진입니다. Mda는 트래핑할 수 없는 이벤트에 대 한 XML 메시지를 생성 합니다. 관리 코드와 비관리 코드 간의 전환 디버깅에 특히 유용 합니다.  
  
 런타임에는 MDA 만들기를 트리거하는 이벤트가 발생 하면 다음 단계를 수행 합니다.  
  
-   호스트 등록 하지 않은 경우는 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 호출 하 여 인스턴스 [iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 알려야 하는 `Event_MDAFired` 으로 이벤트를 런타임 진행 해당 기본값, 호스팅되지 않은 동작입니다.  
  
-   이 이벤트에 대 한 처리기를 등록 하는 호스트 하는 경우 런타임에서 프로세스에 디버거가 연결 되어 있는지 여부를 확인 합니다. 인 경우 런타임은 디버거에서 실행을 중단 합니다. 디버거에서 계속 될 때 호스트를 호출 합니다. 디버거가 연결 되 면 런타임에서 호출 `IActionOnCLREvent::OnEvent` 전달에 대 한 포인터는 `MDAInfo` 인스턴스로 `data` 매개 변수입니다.  
  
 Mda를 활성화 하 고 MDA가 활성화 될 때 알림을 받을 수는 호스트 선택할 수 있습니다. 이 기회 호스트는 기본 동작을 재정의 하 고 프로세스 상태가 손상 되지 않도록 하려면 이벤트를 발생 하는 관리 되는 스레드를 중단 합니다. Mda를 사용 하는 방법에 대 한 자세한 내용은 참조 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
