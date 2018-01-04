---
title: "ICLRPolicyManager::SetActionOnFailure 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4440b36485ed900b5e64adcead2525dbb7d5206e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>ICLRPolicyManager::SetActionOnFailure 메서드
공용 언어 런타임 (CLR)의 오류가 발생할 경우 수행 해야 하는 정책 동작을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `failure`  
 [in] 중 하나는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 의 조치를 사용 하는 오류 유형을 나타내는 값입니다.  
  
 `action`  
 [in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 오류가 발생할 경우 수행할 작업을 나타내는 값입니다. 지원 되는 값 목록은 설명 섹션을 참조 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_INVALIDARG|지정된 된 작업에 대 한 정책 작업을 설정할 수 없습니다 또는 작업에 대 한 정책 작업이 잘못 지정 되었습니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 CLR 즉, 메모리 리소스를 할당 하지 못하면 예외를 throw 합니다. `SetActionOnFailure`호스트를 정책 작업을 실패를 지정 하 여이 동작을 재정의할 수 있습니다. 다음 표에서 조합을 보여 줍니다. [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 및 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 지원 되는 값입니다. (에서 FAIL_ 접두사를 생략 하는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 값입니다.)  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|CodeContract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||N/A||  
|eThrowException|X|X||||N/A||  
|`eAbortThread`|X|X||||N/A|X|  
|`eRudeAbortThread`|X|X||||N/A|X|  
|`eUnloadAppDomain`|X|X||X||N/A|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|N/A|X|  
|`eExitProcess`|X|X||X|X|N/A|X|  
|eFastExitProcess|X|X||X|X|N/A||  
|`eRudeExitProcess`|X|X|X|X|X|N/A||  
|`eDisableRuntime`|X|X|X|X|X|N/A||  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [EClrFailure 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction 열거형](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
