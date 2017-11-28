---
title: "ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee616e1fbd071662a42af856fa2cd51f7bdd5d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>ICLRAppDomainResourceMonitor::GetCurrentAllocated 메서드
가비지 수집 된 메모리를 제외 하지 않고 만들어진 후 응용 프로그램 도메인에서 실행 된 모든 메모리 할당의 바이트의 총 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwAppDomainId`  
 [in] 요청 된 응용 프로그램 도메인의 ID입니다.  
  
 `pBytesAllocated`  
 [out] 모든 메모리 할당의 총 크기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|COR_E_APPDOMAINUNLOADED|응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 관리 되는 관리 되지 않는 버전 <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
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
