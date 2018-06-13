---
title: ICLROnEventManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22dfa99d8069c060a525a9ae2cbef73d6625898
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434105"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager 인터페이스
등록 하 고 공용 언어 런타임 (CLR) 이벤트에 대 한 콜백을 등록을 취소 하기 위해 호스트에 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[RegisterActionOnEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|지정된 된 이벤트에 대 한 콜백 포인터를 등록합니다.|  
|[UnregisterActionOnEvent 메서드](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|지정된 된 이벤트에 대 한 이전에 등록 된 콜백 포인터를 등록 취소합니다.|  
  
## <a name="remarks"></a>설명  
 등록 하 고 이벤트 콜백을 등록 취소, 호스트에 대 한 참조를 가져옵니다 `ICLROnEventManager` 호출 하 여는 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.  
  
> [!NOTE]
>  설명 하는 이벤트 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 서로 다른 스레드의 신호를 보내는 언로드 또는 CLR의 비활성화 하 고 두 번 이상 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [EClrEvent 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
