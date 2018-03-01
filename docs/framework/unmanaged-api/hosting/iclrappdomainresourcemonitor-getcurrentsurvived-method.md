---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 612e27120196d2920b75c030929af1807d4a336f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드
마지막 전체 차단 가비지 수집에도 유지 되 고 현재 응용 프로그램 도메인에서 참조 되는 바이트 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwAppDomainId`  
 [in] 요청 된 응용 프로그램 도메인의 ID입니다.  
  
 `pAppDomainBytesSurvived`  
 [out] 이 응용 프로그램 도메인 보유 하 고 있는 마지막 가비지 수집 후에 남아 있는 바이트 수에 대 한 포인터입니다. 전체 컬렉션 후이 번호는 정확 하 고 완료 합니다. 임시 컬렉션 후이 번호 잠재적으로 완전 하지 않습니다. 이 매개 변수는 `null`일 수 있습니다.  
  
 `pRuntimeBytesSurvived`  
 [out] 마지막 가비지 수집에서 유지 된 바이트의 총 수에 대 한 포인터입니다. 이 숫자를 전체 수집 후에 관리 되는 힙을 저장 된 바이트 수를 나타냅니다. 임시 컬렉션 후이 숫자를 임시 생성에 실시간으로 저장 된 바이트 수를 나타냅니다. 이 매개 변수는 `null`일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|COR_E_APPDOMAINUNLOADED|응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 통계가 한 전체 차단 가비지 컬렉션 후에 업데이트 즉, 모든 세대를 포함 하 고 수집 하는 동안 응용 프로그램을 중지 하는 컬렉션에 발생 합니다. 예를 들어는 <xref:System.GC.Collect?displayProperty=nameWithType> 전체 차단 수집을 수행 하는 메서드 오버 로드 합니다. 동시 가비지 수집이 백그라운드에서 발생 하 고 응용 프로그램을 차단 하지 않습니다.  
  
 `GetCurrentSurvived` 메서드는 관리 되는 관리 되지 않는 버전 <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAppDomainResourceMonitor 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [응용 프로그램 도메인 리소스 모니터링](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
