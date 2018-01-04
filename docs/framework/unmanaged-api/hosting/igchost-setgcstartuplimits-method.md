---
title: "IGCHost::SetGCStartupLimits 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d99212b1ece4d3c0ce9440ac973b8254ebca6dde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits 메서드
0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.  
  
> [!IMPORTANT]
>  부터는 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]세그먼트 크기를 설정할 수 있습니다 및 0 세대의 최대 크기를 보다 큰 값, `DWORD` 를 사용 하 여는 [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SegmentSize`  
 [in] 가비지 수집 시스템에서 사용 하는 세그먼트의 크기입니다.  
  
 `MaxGen0Size`  
 [in] 0 세대에 대 한 최대 크기입니다.  
  
## <a name="remarks"></a>설명  
 `SetGCStartupLimits` 메서드를 한 번만 호출할 수 있습니다. 이러한 값은 나중에 변경할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** GCHost.idl, GCHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IGCHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
