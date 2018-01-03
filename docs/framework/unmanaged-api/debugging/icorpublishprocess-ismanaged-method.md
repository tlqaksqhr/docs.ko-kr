---
title: "ICorPublishProcess::IsManaged 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21fdb09820acb6357fe1457d2f96c3319b3152a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged 메서드
이 프로세스를 참조 하는지 여부를 나타내는 값을 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 관리 코드가 있는 것으로 알려져 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbManaged`  
 [out] 프로세스에 코드를 관리 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다. 값은 `true` 프로세스에 코드를 관리 하는 경우 이렇게 하지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 현재 버전의 이후 `ICorPublishProcess` 관리 코드가 있는 프로세스에만 액세스할 수 있도록 `IsManaged` 항상 반환 `true`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorPublishProcess 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
