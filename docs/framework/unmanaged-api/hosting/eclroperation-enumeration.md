---
title: EClrOperation 열거형
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434247"
---
# <a name="eclroperation-enumeration"></a>EClrOperation 열거형
호스트 정책 작업을 적용할 수는 작업 집합에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|정책 작업을 수행할 때 지정할 수는 <xref:System.AppDomain> 정상적인 (강제) 방식으로 언로드 합니다.|  
|`OPR_AppDomainUnload`|정책 작업을 수행할 때 지정할 수는 <xref:System.AppDomain> 로드 됩니다.|  
|`OPR_FinalizerRun`|호스트 종료 자가 실행 시 수행 될 정책 작업을 지정할 수 있습니다.|  
|`OPR_ProcessExit`|호스트는 프로세스가 종료 시 수행 될 정책 작업을 지정할 수 있습니다.|  
|`OPR_ThreadAbort`|호스트는 스레드가 중단 시 수행 될 정책 작업을 지정할 수 있습니다.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|호스트 정책 작업을 코드의 중요 한 영역에서 잘못 된 스레드 중단이 발생 하는 경우 수행할 지정할 수 있습니다.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|호스트 정책 작업을 코드의 중요 하지 않은 지역에 잘못 된 스레드 중단이 발생할 경우 수행할 수를 지정할 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 공용 언어 런타임 (CLR) 안정성 인프라 오류와 구분 중단 및 리소스 할당 코드와 코드의 중요 하지 않은 영역에서 발생 하는 중요 한 영역에서 발생 하는 합니다. 이러한 구분은 호스트 코드에서 오류가 발생 하는 위치에 따라 서로 다른 정책을 설정할 수 있도록 설계 되었습니다.  
  
 A *코드의 중요 영역* CLR에서 해당 작업을 중단 하거나 리소스에는 현재 작업에만 영향을 줍니다에 대 한 요청을 완료 하려면 실패 줄 수 없는 공간이 있습니다. 예를 들어 잠금을 보유 메모리 할당 요청을 수행할 때 오류를 나타내는 HRESULT를 수신 하는 작업, 것으로 부족 단순히 해당 작업의 안정성을 중단 하는 <xref:System.AppDomain>때문에 <xref:System.AppDomain> 다른 포함 될 수 있습니다 동일한 잠금으로 인해 대기 하는 작업입니다. 중단할 현재 작업 발생할 수 있습니다 이러한 다른 작업이 응답 하지 (또는 중지)을 계속 합니다. 이 경우 호스트는 전체를 언로드할 수 있어야 <xref:System.AppDomain> 위험 잠재적 불안정 하는 대신 합니다.  
  
 A *코드 영역을 경계*, 반면에 있는 CLR는 중단 또는 실패는 오류가 발생 하는 작업에만 영향이 보장할 수는 영역을입니다.  
  
 또한 CLR 정상적이 고 정상적인 잘못 중단을 구분합니다. 일반적으로 정상적으로 중단 강제 중단을 사용 하면 이러한 보장 하지는 작업을 중단 하기 전에 예외 처리 루틴 및 종료자를 실행 하기 위한 모든 작업을 만듭니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [EClrFailure 열거형](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction 열거형](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
