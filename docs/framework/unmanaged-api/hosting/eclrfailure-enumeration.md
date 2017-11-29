---
title: "EClrFailure 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94358fd0626fa17f1fd6d3c365aff79f89dde467
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="eclrfailure-enumeration"></a>EClrFailure 열거형
호스트 정책 작업 설정할 수 있는 오류를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|코드는 중요 하지 않은 영역에서 리소스 (예: 스레드, 메모리의 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.|  
|`FAIL_CriticalResource`|코드의 중요 한 영역에서 리소스 (예: 스레드, 메모리의 블록 또는 잠금)를 할당 하는 동안 오류가 발생 했습니다.|  
|`FAIL_FatalRuntime`|공용 언어 런타임 (CLR)을 프로세스의 관리 되는 코드를 실행할 수 없습니다. 예측이 호스팅 모든 함수에 대 한 호출 HOST_E_CLRNOTAVAILABLE HRESULT 값을 반환합니다.|  
|`FAIL_OrphanedLock`|반환 하면 잠금을 해제 하는 스레드 못한는 <xref:System.AppDomain> 개체입니다. 호스트는이 오류는 스레드가 중단 되도록를 설정할 수 없습니다.|  
|`FAIL_StackOverflow`|스택 오버플로가 발생 했습니다.|  
|`FAIL_AccessViolation`|보호 된 메모리를 읽거나 하려고 했습니다. 지원 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.|  
|`FAIL_CodeContract`|코드 계약 오류가 발생 했습니다. 참조 [계약 코드](../../../../docs/framework/debug-trace-profile/code-contracts.md)합니다.|  
  
## <a name="remarks"></a>설명  
 참조는 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 목록은 메서드 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 오류 상태에 대 한 정책 동작을 지정 하는 호스트가 사용할 수 있습니다. 코드의 중요 하 고 중요 하지 않은 영역에 대 한 자세한 내용은 참조 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
