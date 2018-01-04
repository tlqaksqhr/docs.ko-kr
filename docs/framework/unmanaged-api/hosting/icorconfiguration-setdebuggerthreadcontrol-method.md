---
title: "ICorConfiguration::SetDebuggerThreadControl 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46bd2b7a40cbcf4f68b8c2f62fea466aa17f2d31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a>ICorConfiguration::SetDebuggerThreadControl 메서드
디버깅 서비스 디버깅을 위해 공용 언어 런타임 (CLR) 스레드를 차단 하 여 차단 해제를 호출 하는 콜백 인터페이스를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDebuggerThreadControl`  
 [in] 에 대 한 포인터는 [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) 개체를 차단 하 고 디버깅 서비스에 의해 스레드 차단을 해제 하는 방법에 대 한 호스트에 알립니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorConfiguration 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
