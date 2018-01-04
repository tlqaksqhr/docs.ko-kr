---
title: "ICorPublishProcess::EnumAppDomains 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.EnumAppDomains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 938c022788d5ed9f0e28f794432017748dc096e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains 메서드
이 참조 하는 프로세스에서 응용 프로그램 도메인에 대 한 열거자를 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 주소에 대 한 포인터는 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) 이 프로세스의 응용 프로그램 도메인의 컬렉션을 반복할 수 있는 인스턴스.  
  
## <a name="remarks"></a>설명  
 응용 프로그램 도메인 목록에 존재 하는 응용 프로그램 도메인의 스냅숏을 기반 때는 `EnumAppDomains` 메서드를 호출 합니다. 새로운 최신 목록을 만들려면이 메서드를 두 번 이상 호출할 수 있습니다. 기존 목록이이 방법의 후속 호출에 의해 적용 되지 않습니다.  
  
 프로세스가 종료 된 경우 `EnumAppDomains` CORDBG_E_PROCESS_TERMINATED HRESULT 값와 함께 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorPublishProcess 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
