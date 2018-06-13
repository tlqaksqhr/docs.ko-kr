---
title: ICLRHostBindingPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 637803c509935fdff080802f66f9f73ab8cf25e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431990"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>ICLRHostBindingPolicyManager 인터페이스
현재 바인딩 정책을 평가 하 고 지정된 된 어셈블리에 대 한 정책 변경 내용을 통신 하기 위해 호스트에 대 한 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EvaluatePolicy 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|호스트를 대신 하 여 바인딩 정책을 평가합니다.|  
|[ModifyApplicationPolicy 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|지정된 된 어셈블리에 대 한 바인딩 정책 수정 하 고 정책의 새 버전을 만듭니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
