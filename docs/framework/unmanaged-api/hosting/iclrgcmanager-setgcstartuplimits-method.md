---
title: ICLRGCManager::SetGCStartupLimits 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cbcd3ae758add4beec24959314d2cf806c2a2b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435695"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits 메서드
가비지 수집 세그먼트의 크기와 0 세대 가비지 수집 시스템의 최대 크기를 설정 합니다.  
  
> [!IMPORTANT]
>  부터는 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]세그먼트 크기를 설정할 수 있습니다 및 0 세대의 최대 크기를 보다 큰 값, `DWORD` 를 사용 하 여는 [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SegmentSize`  
 [in] 가비지 수집 세그먼트의 지정 된 크기입니다.  
  
 최소 세그먼트 크기는 4MB입니다. 1mb 단위로 증가 또는 더 큰 세그먼트 수 있습니다.  
  
 `MaxGen0Size`  
 [in] 0 세대에 대 한 지정 된 최대 크기입니다.  
  
 0 세대의 최소 크기는 64KB입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 값은 `SetGCStartupLimits` 집합을 한 번만 지정할 수 있습니다. 나중에 대 한 호출이 `SetGCStartupLimits` 무시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [자동 메모리 관리](../../../../docs/standard/automatic-memory-management.md)  
 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
