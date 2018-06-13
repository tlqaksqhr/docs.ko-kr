---
title: ICLRDebugManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d123177bf9f1b5eee1a2ba4d9b7f2042ddc07aa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434941"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager 인터페이스
호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginConnection 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|식별자 및 이름을 사용 하 여 작업을 연결 하는 호스트와 디버거 사이 새 연결을 설정 합니다.|  
|[EndConnection 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|작업 목록 및 식별자 및 이름을 사이의 연결을 제거 합니다.|  
|[GetDacl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|이 메서드가 구현되지 않았습니다.|  
|[IsDebuggerAttached 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|[SetConnectionTasks 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|연결 목록이 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 라는 이름과 식별자를 사용 하 여 인스턴스.|  
|[SetDacl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|이 메서드가 구현되지 않았습니다.|  
|[SetSymbolReadingPolicy 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다. 정책을 호출 스택의 줄 번호와 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 디버깅 시나리오에서는 호스트 자체 프로그래밍 논리에 따라 작업을 그룹화 할 보겠습니다. 예를 들어 그룹화 하는 프로세스에서 실행 중인 모든 작업을 보는 대신 개발자의 Api에 필요한 작업에만 표시 되도록을 사용 합니다. `ICLRDebugManager` 이러한 그룹화를 구현 하는 호스트 수 있습니다.  
  
> [!IMPORTANT]
>  세 가지 `ICLRDebugManager` 메서드 `BeginConnection`, `SetConnectionTasks` 및 `EndConnection`, 서로 종속 됩니다. 예상 대로 작동 하는 지정 된 순서로 호출 해야 합니다.  
  
 그룹화 식별자 및 호스트 그룹화에 할당 하는 공용 언어 런타임 (CLR)에 대 한 아무런 의미가 있습니다. CLR는 단순히 디버거에 따라 정보를 전달합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
