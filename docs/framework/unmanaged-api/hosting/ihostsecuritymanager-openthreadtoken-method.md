---
title: "IHostSecurityManager::OpenThreadToken 메서드"
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
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b5c39632d7628d30149a0a0278f9bf6c865bc29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken 메서드
현재 실행 중인 스레드와 연결 된 임의 액세스 토큰을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 [in] 요청 된 유형의 스레드 토큰에 대 한 액세스를 지정 하는 액세스 값의 마스크입니다. 이러한 값은 win32에서 정의 `OpenThreadToken` 함수입니다. 요청 된 액세스 형식은 토큰의 임의 액세스 제어 목록 (DACL)의 액세스를 허용 하거나 거부할 유형을 기준으로 합니다.  
  
 `bOpenAsSelf`  
 [in] `true` 호출 스레드가;에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사 수행 수를 지정 하려면 `false` 액세스 확인을 수행 하는 호출 스레드 자체에 대 한 보안 컨텍스트를 사용 하 여 지정할 수 있습니다. 스레드는 클라이언트를 가장 하는 경우 클라이언트 프로세스의 보안 컨텍스트 수 있습니다.  
  
 `phThreadToken`  
 [out] 새로 열린된 액세스 토큰에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostSecurityManager::OpenThreadToken`동작 마찬가지로 동일한 이름 가진 해당 Win32 함수에 Win32 함수에서는 임의의 스레드에 대 한 핸들에 전달할 호출자를 허용 한다는 점을 제외 하는 동안 `IHostSecurityManager::OpenThreadToken` 만 호출 스레드에 연결 된 토큰을 엽니다.  
  
 `HANDLE` 형식이 COM 호환, 즉, 해당 크기는 운영 체제에 적용 하 고 사용자 지정 마샬링 필요 합니다. 따라서이 토큰은 CLR과 호스트 간에 프로세스 에서만 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
