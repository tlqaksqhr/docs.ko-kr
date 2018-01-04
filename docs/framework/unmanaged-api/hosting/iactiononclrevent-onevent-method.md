---
title: "IActionOnCLREvent::OnEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IActionOnCLREvent.OnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfba70cb1e0daf230abd16af6e24b4671334f20d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iactiononclreventonevent-method"></a>IActionOnCLREvent::OnEvent 메서드
이벤트에 대 한 호출을 사용 하 여 등록 된 콜백이 수행 된 [iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `event`  
 [in] 중 하나는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 값 이벤트의 형식을 나타냅니다.  
  
 `data`  
 [in] 에 대 한 세부 정보를 포함 하는 개체에 대 한 포인터 `event`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`OnEvent`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드는 동안 이벤트가 취소 되었거나 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 이후에 모든 호스팅 메서드를 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `data` 매개 변수는 지정 되지 않은 형식의 개체에 대 한 포인터입니다. 경우는 `event` 매개 변수는 `Event_DomainUnload`, `data` 에 대 한 숫자 식별자는 <xref:System.AppDomain> 는 언로드 되었습니다. 호스트 키로이 식별자를 사용 하 여 적절 한 조치를 걸릴 수 있습니다.  
  
 경우 `event` 은 `Event_MDAFired`, `data` 에 대 한 포인터는 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) 메시지 출력에서는 관리 되는 디버깅 도우미 (MDA) 포함 된 인스턴스. Mda는 clr 디버깅을 트래핑할 수 없는 이벤트에 대 한 XML 메시지를 생성 하 여 개발자는 데 도움이 되는 기능입니다. 이러한 메시지 디버깅 관리 및 비관리 코드 간의 전환에서 특히 유용할 수 있습니다. 자세한 내용은 참조 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [EClrEvent 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLROnEventManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [MDAInfo 구조체](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
