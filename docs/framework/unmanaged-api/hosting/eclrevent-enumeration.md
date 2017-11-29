---
title: "EClrEvent 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrEvent
helpviewer_keywords: EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0585cea00865f4798c57ef5276076c2b0a5ff284
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="eclrevent-enumeration"></a>EClrEvent 열거형
호스트 콜백을 등록할 수 있는 공용 언어 런타임 (CLR) 이벤트에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`Event_ClrDisabled`|CLR 오류가 지정합니다.|  
|`Event_DomainUnload`|특정 언로드 지정 <xref:System.AppDomain>합니다.|  
|`Event_MDAFired`|관리 디버깅 도우미 (MDA) 메시지에 생성 되었음을 지정 합니다.|  
|`Event_StackOverflow`|스택 오버플로 오류가 발생 했는지를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트에서 설명 된 이벤트 형식에 대 한 콜백을 등록할 수 `EClrEvent` 의 메서드를 호출 하 여는 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) 인터페이스입니다. 호스트를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다는 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.  
  
 `Event_CLRDisabled` 및 `Event_DomainUnload` 두 번 이상 및는 언로드 또는 CLR의 비활성화를 알리기 위해 서로 다른 여러 스레드에서 이벤트가 발생할 수 있습니다.  
  
 `Event_MDAFired` 이벤트 발생 만들기는 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) MDA 메시지의 세부 정보가 포함 된 인스턴스. Mda에 대 한 자세한 내용은 참조 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
