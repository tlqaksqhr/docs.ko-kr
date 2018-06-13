---
title: GetCLRIdentityManager 함수
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a0672196ebaea5c91139851b89a7476ff6363b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430797"
---
# <a name="getclridentitymanager-function"></a>GetCLRIdentityManager 함수
공용 언어 런타임 (CLR) id를 관리할 수 있는 인터페이스에 대 한 포인터를 가져옵니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] A `REFIID` 얻으려고 하는 인터페이스를 지정 하는 (인터페이스 식별자)입니다. 이 값은 IID_ICLRAssemblyIdentityManager 또는 IID_ICLRHostBindingPolicyManager 중 하나 여야 합니다.  
  
 `ppManager`  
 [out] 주소에 대 한 포인터는 [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) 또는 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 개체입니다.  
  
## <a name="remarks"></a>설명  
 호출 된 [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) 함수에 대 한 포인터를는 `GetCLRIdentityManager` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorWks.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
