---
title: "EHostBindingPolicyModifyFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb985cf2f34719b3aed9397155bd9d538b57dc3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags 열거형
호스트를 정책 수정 내용을 소스 어셈블리의 대상 어셈블리에 적용할 때 공용 언어 런타임 (CLR) 수행할 리디렉션 형식을 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|CLR에서 대상 어셈블리의 소스 어셈블리의 정책 값을 연결할 됩니다 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|CLR 기본 작업을 수행할 것을 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|CLR 설정 한다는 대상 어셈블리의 정책 값을 최대값을 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|CLR에서 대상 어셈블리의 정책 값 소스 어셈블리의 사용을 바꿉니다 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 [iclrhostbindingpolicymanager:: Modifyapplicationpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 형식의 매개 변수를 사용 하는 메서드 `EHostBindingPolicyModifyFlags`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRHostBindingPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
