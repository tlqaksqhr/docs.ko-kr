---
title: "ICLRGCManager2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b025ec31e3797fec3ac184929f1274cb5f68501b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2 인터페이스
공용 언어 런타임의 가비지 수집 시스템과 상호 작용 하는 데 사용 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetGCStartupLimitsEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|가비지 수집 세그먼트의 크기와 0 세대 가비지 수집 시스템의 최대 크기를 설정 합니다. 0 세대 및 세그먼트 크기 보다 큰 수 있도록 `DWORD`합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스에서 상속 된 [ICLRGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)합니다.  
  
 관리 되는 가비지 수집 메커니즘을 구현 하는 공용 언어 런타임 (CLR) <xref:System.GC> 유형입니다. 가비지 수집 시스템에 대 한 자세한 내용은 참조 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [자동 메모리 관리](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS 구조체](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [4 및 4.5.NET Framework에 추가 된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
