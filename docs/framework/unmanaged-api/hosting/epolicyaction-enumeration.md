---
title: "EPolicyAction 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction 열거형
호스트에서 설명 하는 작업에 대해 설정할 수 정책 작업을 설명 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 에 정의 된 오류 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAbortThread`|공용 언어 런타임 (CLR) 스레드를 적절 하 게 중단 하도록 지정 합니다. 모든 실행 시도 포함 하는 정상적인 중단 `finally` 모든 차단 `catch` 스레드 중단 및 종료자와 관련 된 블록입니다.|  
|`eDisableRuntime`|CLR에서 사용할 수 없는 상태를 입력 해야 지정 합니다. 영향을 받는 프로세스에 관리 되는 코드를 실행 하는 더 이상 및 clr에서 스레드는 차단 됩니다.|  
|`eExitProcess`|CLR가 종료자를 실행 하 고 정리 및 로깅 작업 수행을 포함 하는 프로세스의 정상 종료를 시도해 야 지정 합니다.|  
|`eFastExitProcess`|CLR 프로세스를 종료 하도록 즉시 종료자를 실행 하거나 정리 및 로깅 작업을 수행 하지 않고 지정 합니다. 디버거에 디버거 알림이 전송 됩니다.|  
|`eNoAction`|아무 작업도 수행 해야 있는지를 지정 합니다.|  
|`eRudeAbortThread`|CLR가 잘못 된 스레드 중단이 수행 하도록 지정 합니다. 항목만 `catch` 및 `finally` 블록으로 표시 된 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.|  
|`eRudeExitProcess`|CLR 종료자를 실행 하거나 작업을 기록 하지 않고 프로세스를 종료 하도록 지정 합니다.|  
|`eRudeUnloadAppDomain`|CLR의 잘못 된 언로드를 수행 하도록 지정 된 <xref:System.AppDomain>합니다. 으로 표시 된 유일한 종료자 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다. 마찬가지로, 모든 스레드가이 <xref:System.AppDomain> 여 스택에 수신는 `ThreadAbortException`, 되지만 `catch` 및 `finally` 블록으로 표시 된 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.|  
|`eThrowException`|메모리 부족, 버퍼 오버플로 등과 같은 조건에 적합 한 예외가 발생 하도록 지정 합니다.|  
|`eUnloadAppDomain`|지정 하는 <xref:System.AppDomain> 로드 해야 합니다. CLR은 종료자를 실행 하려고 시도 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트의 메서드를 호출 하 여 정책을 실행 하도록 설정 하는 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) 인터페이스입니다. 강제 하 고 정상적으로 중단 하는 방법에 대 한 정보를 참조 하십시오.는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 열거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [EClrFailure 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
