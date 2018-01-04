---
title: "ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 018dc40895a79788a9eef20082d764db0b2265c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드
지정된 된 어셈블리에 대 한 바인딩 정책 수정 하 고 정책의 새 버전을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzSourceAssemblyIdentity`  
 [in] 수정 하는 어셈블리의 id입니다.  
  
 `pwzTargetAssemblyIdentity`  
 [in] 수정된 된 어셈블리의 새 id입니다.  
  
 `pbApplicationPolicy`  
 [in] 수정 하려면 어셈블리에 대 한 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `cbAppPolicySize`  
 [in] 바인딩 정책 교체의 크기입니다.  
  
 `dwPolicyModifyFlags`  
 [in] 논리 OR 조합 [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) 리디렉션의 제어를 나타내는 값입니다.  
  
 `pbNewApplicationPolicy`  
 [out] 새 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `pcbNewAppPolicySize`  
 [out에서] 새 바인딩 정책 버퍼의 크기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|정책이는 성공적으로 수정 되었습니다.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`또는 `pwzTargetAssemblyIdentity` 가 null 참조입니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `ModifyApplicationPolicy` 메서드를 두 번 호출할 수 있습니다. 첫 번째 호출에 대 한 null 값을 지정 해야는 `pbNewApplicationPolicy` 매개 변수입니다. 이 호출에 대 한 필요한 값으로 반환 합니다 `pcbNewAppPolicySize`합니다. 두 번째 호출에 대 한이 값을 제공 해야 `pcbNewAppPolicySize`에 대 한 해당 크기의 버퍼를 가리키도록 `pbNewApplicationPolicy`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRHostBindingPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
