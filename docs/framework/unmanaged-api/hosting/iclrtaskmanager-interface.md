---
title: "ICLRTaskManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3144338ddce262aaa6772f588a4f1a652cc57e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager 인터페이스
공용 언어 런타임 (CLR) 명시적으로 요청 하는 호스트를 사용할 수 있는 메서드는 새 작업 만들기, 현재 실행 중인 작업을 가져오고 설정 언어와 문화권을 작업에 대 한 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|CLR을 새로 만들 명시적 요청 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스.|  
|[GetCurrentTask 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|가져옵니다는 `ICLRTask` 현재 실행 중인 작업을 나타내는 인스턴스입니다.|  
|[GetCurrentTaskType 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|현재 실행 중인 작업의 유형을 가져옵니다.|  
|[SetLocale 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|호스트가 현재 실행 중인 작업에 대 한 로캘 식별자를 수정 하는 CLR에 알립니다.|  
|[SetUILocale 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|호스트가 현재 실행 중인 작업에서 사용자 인터페이스 로캘 식별자를 수정 하는 공용 언어 런타임 알립니다.|  
  
## <a name="remarks"></a>설명  
 호스트 된 환경에서 실행 되는 각 작업이 호스트 측에 대 한 표현을 두 (인스턴스의 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) CLR 쪽에 (인스턴스의 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). 호스트 또는 CLR, 작업의 만들기를 시작할 수 있지만 호스트 측 표현을 호스트와 작업에 대 한 CLR 간의 성공적으로 통신을 위해 해당 CLR 측 표현과와 연결 되어야 합니다. 두 개체가 만들고 인스턴스화하기 전에 운영 체제 스레드에 대해 관리 코드를 실행 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
