---
title: IGCHost 인터페이스
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a77cd85c0fafd9994418693c8d3c4b148c34dbe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437666"
---
# <a name="igchost-interface"></a>IGCHost 인터페이스
가비지 수집의 일부 측면을 제어 하기 위한 가비지 수집 시스템에 대 한 정보를 얻기 위한 메서드를 제공 합니다.  
  
> [!NOTE]
>  부터는 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수 있습니다는 [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기와를 설정 하려면 0 세대 가비지 수집 시스템의 최대 크기 값 보다 큰 메서드는 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) 메서드.  
  
> [!NOTE]
>  이 인터페이스는 전문가만 사용 합니다. 부적절 하 게 사용 하는 경우에 응용 프로그램의 성능 영향을 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Collect 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 대 한 컬렉션을 수행 합니다.|  
|[GetStats 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|가비지 수집 시스템의 현재 상태에 대 한 통계를 가져옵니다.|  
|[GetThreadStats 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|가비지 수집에 대 한 스레드 통계를 가져옵니다.|  
|[SetGCStartupLimits 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.|  
|[SetVirtualMemLimit 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|런타임 가상 메모리의 최대 크기를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** GCHost.idl, GCHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
