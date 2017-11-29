---
title: "ModuleBindInfo 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6488503e0300530b22c0c6f904e11db7f5d5b41c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo 구조체
참조 된 모듈 및 포함 된 어셈블리에 대 한 자세한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dwAppDomainId`|에 대 한 고유 식별자는 `IStream` 에 대 한 호출에서 반환 하는 [ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) 메서드 로드 되도록은 참조 된 모듈입니다.|  
|`lpAssemblyIdentity`|참조 된 모듈을 포함 하는 어셈블리에 대 한 고유 식별자입니다.|  
|`lpModuleName`|참조 된 모듈의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 `ModuleBindInfo`에 대 한 매개 변수로 전달 됩니다 `IHostAssemblyStore::ProvideModule`합니다. 고유 식별자를 제공 하는 호스트 `dwAppDomainId` 공용 언어 런타임 (CLR). 호출한 후에 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 런타임 식별자를 사용 하 여 결정 메서드가 반환 하는지 여부를의 내용을 `IStream` 매핑 되었습니다. 이 경우 런타임에서 스트림을 다시 매핑하는 것이 아니라 기존 복사본을 로드 합니다. 또한 공용 언어 런타임은이 식별자에 대 한 호출에서 반환 되는 스트림에 대 한 조회 키로는 `IHostAssemblyStore::ProvideAssembly` 메서드. 따라서 식별자 어셈블리 요청에 대 한 모듈 요청 및 고유 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [AssemblyBindInfo 구조체](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
