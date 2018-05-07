---
title: IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0da548d5d5cc22eb6754859a802afa4d82fac89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트에서는 공용 언어 런타임 (CLR)를 로드 하는 어셈블리의 목록을 나타내는입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppReferenceList`  
 [out] 주소에 대 한 포인터는 `ICLRAssemblyReferenceList` 호스트에서는 로드 하기 위해 CLR 어셈블리에 대 한 참조의 목록이 들어 있는입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|요청 된 작업에 대 한 참조 목록을 만드는 데 사용할 수 있는 메모리가 부족 했습니다 `ICLRAssemblyReferenceList`합니다.|  
  
## <a name="remarks"></a>설명  
 CLR 참조는 다음과 같은 지침 집합을 사용 하 여 해결할 수 있습니다.  
  
-   반환 하는 어셈블리 참조의 목록을 확인 먼저 `GetNonHostStoreAssemblies`합니다.  
  
-   어셈블리의 목록에 표시 하는 경우 CLR에 정상적으로 바인딩합니다.  
  
-   어셈블리 목록에 나타나지 않으며 호스트의 구현에서 제공 하는 경우 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR에서는 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 호스트가 제공할 수 있도록 하는 바인딩할 어셈블리입니다.  
  
-   그렇지 않으면 CLR 어셈블리에 바인딩하는 실패 합니다.  
  
 호스트 설정 하는 경우 `ppReferenceList` null이 고, CLR 첫 번째 프로브를 전역 어셈블리 캐시 호출 `ProvideAssembly`, 다음 어셈블리 참조를 확인 하려면 응용 프로그램 기준 위치를 탐색 합니다.  
  
> [!NOTE]
>  CLR은 호출 초기화 될 `GetNonHostStoreAssemblies` 한 번만 합니다. 메서드가 다시 호출 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
