---
title: "EContextType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd068816c5a642a7a8230fc14045e3f43980936c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="econtexttype-enumeration"></a>EContextType 열거형
현재 실행 중인 스레드의 보안 컨텍스트를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eCurrentContext`|공용 언어 런타임 (CLR)를 호출 시 현재 스레드에서 컨텍스트를 나타내는 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드나에 대 한 호출에서 CLR에서 요청 컨텍스트는 [ Ihostsecuritymanager:: Setsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) 메서드.|  
|`eRestrictedContext`|호스트에는 가비지 수집기 또는 클래스나 모듈 생성자와 같이 더 낮은 권한 컨텍스트를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 CLR 제공 중 하나는 `EContextType` 값에 대 한 호출에 매개 변수 값으로는 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
