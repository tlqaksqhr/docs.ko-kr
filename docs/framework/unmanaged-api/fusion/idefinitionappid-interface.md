---
title: "IDefinitionAppId 인터페이스"
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
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247edbe300bbb93ddbdd4260109999fd33b08006
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 인터페이스
현재 범위에서 응용 프로그램을 정의 하는 코드에 대 한 고유 식별자를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|이 코드를 표현 하는 형식이 지정 된 문자열을 가져옵니다 `IDefinitionAppId` 개체입니다.|  
|`IDefinitionAppId::put_Codebase`|이 코드를 설정 `IDefinitionAppId` 를 지정 된 형식의 문자열 값입니다.|  
|`IDefinitionAppId::EnumAppPath`|한 인터페이스 포인터를 가져옵니다는 [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) 현재 응용 프로그램 경로에 어셈블리를 포함 하는 개체입니다.|  
|`IDefinitionAppId::SetAppPath`|지정 된 참조 하는 값을 현재 범위에서 어셈블리에 대 한 응용 프로그램 경로 설정 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 개체입니다.|  
|`IDefinitionAppId::get_SubscriptionId`|이 구독에 대 한 토큰 식별자의 문자열 표현에 대 한 포인터를 가져옵니다 `IDefinitionAppId` 개체입니다.|  
|`IDefinitionAppId::put_SubscriptionId`|이 구독에 대 한 토큰 식별자를 설정 `IDefinitionAppId` 개체를 지정 된 문자열 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Isolation.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
