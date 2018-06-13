---
title: ICLRHostProtectionManager::SetProtectedCategories 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6c93566d0909f1dbef46862760d47ede478d51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434540"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories 메서드
관리 되는 형식과 멤버의 범주는 부분적으로 신뢰할 수 있는 코드에서 실행에서 차단 해야 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `categories`  
 [in] 조합을 [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) 값을 나타내는 관리 되는 형식과 멤버의 범주는 부분적으로 신뢰할 수 있는 코드에서 실행에서 차단 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 각 `EApiCategories` 값은 관리 되는 형식과 멤버의 목록을 나타냅니다. `EApiCategories` 열거형 및 `SetProtectedCategories` 메서드 직접 관련 된 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute> 관리 되는 형식 및 해당 범주에서 설명 하는 기능을 노출 하는 멤버를 표시 하는 데 사용 되는 클래스 `EApiCategories`합니다. 자세한 내용은 참조 <xref:System.Security.Permissions.HostProtectionAttribute> 및 <xref:System.Security.Permissions.HostProtectionResource> 에 해당 하는 열거형 `EApiCategories`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [EApiCategories 열거형](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRHostProtectionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
