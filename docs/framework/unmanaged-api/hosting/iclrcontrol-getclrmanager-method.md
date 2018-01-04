---
title: "ICLRControl::GetCLRManager 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl.GetCLRManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 197a3818de8d0b17331a9f9ac422ecaabb230a50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager 메서드
공용 언어 런타임 (CLR)를 구성 하는 호스트 צ ְ ײ 관리자 형식의 모든 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] `IID` 반환할 관리자 유형의 합니다. 다음 `IID` 값이 지원 됩니다.  
  
-   IID_ICLRDebugManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)합니다.  
  
-   IID_ICLRErrorReportingManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)합니다.  
  
-   IID_ICLRGCManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)합니다.  
  
-   IID_ICLRHostProtectionManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)합니다.  
  
-   IID_ICLROnEventManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)합니다.  
  
-   IID_ICLRPolicyManager:를 지정 하는 `ppObject` 유형 중 하나가 됩니다 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)합니다.  
  
-   IID_ICLRTaskManager: speciries 하 `ppObject` 유형 중 하나가 됩니다 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)합니다.  
  
 `ppObject`  
 [out] 요청 된 관리자 또는 관리자 잘못 된 형식이 요청 하는 경우에 null에 대 한 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_NOINTERFACE|인터페이스 형식이 지원 되지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [IHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
