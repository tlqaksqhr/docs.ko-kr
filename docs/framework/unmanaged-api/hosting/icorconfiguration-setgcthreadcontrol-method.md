---
title: "ICorConfiguration::SetGCThreadControl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b6b28b67f924df4d7f587d0364bce2a853f60b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>ICorConfiguration::SetGCThreadControl 메서드
가비지 컬렉션에 대 한 차단 될 런타임 외 작업에 대 한 스레드를 예약 하기 위한 콜백 인터페이스를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pGCThreadControl`  
 [in] 에 대 한 포인터는 [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) 개체 런타임 외 작업에 대 한 스레드 일시 중단 하는 방법에 대 한 호스트입니다.  
  
## <a name="remarks"></a>설명  
 호스트 내에서 선택할 수 있습니다는 [igcthreadcontrol:: Threadisblockingforsuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) 콜백 스레드 일정을 변경 하려면 여부입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorConfiguration 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
