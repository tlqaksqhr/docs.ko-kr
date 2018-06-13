---
title: EClrUnhandledException 열거형
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eeff8aa0336c0c497e306825c6c77f4f8745ca7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431807"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException 열거형
사용자 코드에서 처리 되지 않은 예외를 관리 하기 위한 사용 가능한 옵션에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|기본 동작이 발생 하도록 지정 합니다. 프로세스 삭제 됩니다.|  
|`eHostDeterminedPolicy`|공용 언어 런타임 (CLR) 처리 되지 않은 예외를 무시 하 고 이후 작업을 결정 하 고 호스트를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 이전 버전 동일 CLR을 지정 하려면 사용 된 `eHostDeterminedPolicy` 멤버입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [EClrFailure 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EClrOperation 열거형](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetUnhandledExceptionPolicy 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
