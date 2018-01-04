---
title: "IHostAssemblyManager::GetAssemblyStore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 347947622601475147663b8838bef5f36a1f7e32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a>IHostAssemblyManager::GetAssemblyStore 메서드
한 인터페이스 포인터를 가져옵니다는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 호스트에 의해 로드 된 어셈블리 목록을 나타내는입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppAssemblyStore`  
 [out] 에 대 한 함수 포인터는 `IHostAssemblyStore` 인스턴스에 지정 하거나 호스트를 구현 하지 않는 경우 null `IHostAssemblyStore`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetAssemblyStore`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_NOINTERFACE|호스트의 구현을 제공 하지 않는 `IHostAssemblyStore`합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostAssemblyStore`호스트 어셈블리와 모듈은 CLR과 별도로 바인딩하는 데 사용할 수 있는 메서드를 제공 합니다. 일반적으로 호스트 파일 시스템 이외의 다른 형식을 로드할 수 있도록 하려면 어셈블리 저장소를 제공 합니다.  
  
> [!NOTE]
>  호스트를 구현 하지 않는 경우 `IHostAssemblyStore`, `GetAssemblyStore` 은 E_NOINTERFACE의 HRESULT 값을 반환 해야 하 고 설정할지 `ppAssemblyStore` null로 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
