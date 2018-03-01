---
title: "ICLRRuntimeInfo::IsLoadable 메서드"
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
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable 메서드
이 인터페이스와 연결 된 런타임을 고려 하는 현재 프로세스에 로드할 수 있는지 여부를 나타냅니다. 이미 프로세스에 로드 될 수 있는 다른 런타임과 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbLoadable`  
 [out] `true` 현재 프로세스에 로드 되 고, 그렇지 않으면이 런타임 수 있으면 `false`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pbLoadable`가 null인 경우|  
  
## <a name="remarks"></a>설명  
 다른 런타임 프로세스에 이미 로드 하 고이 인터페이스와 연결 된 런타임 종속 프로세스-병렬 실행을 위해 로드할 수 있습니다 `pbLoadable` 반환 `true`합니다. 두 개의 런타임-함께 in-process로 실행할 수 없는 경우 `pbLoadable` 반환 `false`합니다. 예를 들어, 공용 언어 런타임 (CLR) 버전 4 나란히 CLR 버전 2.0과 같은 프로세스에서 또는 CLR 버전 1.1 실행할 수 있습니다. 그러나 CLR 버전 1.1과 CLR 버전 2.0-병렬 프로세스를 실행할 수 없습니다.  
  
 경우에 런타임이 프로세스에 로드 됩니다,이 메서드는 항상 반환 `true`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRRuntimeInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
