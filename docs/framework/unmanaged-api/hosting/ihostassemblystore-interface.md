---
title: "IHostAssemblyStore 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c795d4baa3030817299f23c3dadf4caf7a5edc5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore 인터페이스
호스트 별도로 공용 언어 런타임 (CLR) 어셈블리와 모듈을 로드 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ProvideAssembly 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|참조 되지 않은 어셈블리에 대 한 참조는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에 대 한 호출에서 반환 된 [ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)합니다.|  
|[ProvideModule 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|연결된 (포함된 되지 않은) 리소스 파일 또는 어셈블리 내의 모듈을 확인 합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostAssemblyStore`호스트 효율적으로 어셈블리 id를 기준으로 어셈블리를 로드 하는 방법을 제공 합니다. 반환 하 여 어셈블리를 로드 하는 호스트 `IStream` 직접적으로 바이트를 가리키는 인스턴스.  
  
 CLR 호스트에 구현 여부를 결정 `IHostAssemblyStore` 호출 하 여 `IHostAssemblyManager::GetNonHostAssemblyStores` 초기화 시. 이렇게 하면 호스트, 예를 들어 사용자 어셈블리에 대 한 바인딩을 제어할 수 있지만 런타임에서.NET Framework 어셈블리에 바인딩할 수 있습니다.  
  
> [!NOTE]
>  구현을 제공 한다는 측면에서 `IHostAssemblyStore`, 호스트에서 참조 되지 않는 모든 어셈블리를 확인 하도록 지정는 `ICLRAssemblyReferenceList` 에서 반환 된 `IHostAssemblyManager::GetNonHostStoreAssemblies`합니다.  
  
> [!NOTE]
>  제공 된 대로.NET Framework 버전 2.0에는 어셈블리의 네이티브 이미지를 로드 하기 위해 호스트에 대 한는 방법을 제공 하지 않습니다는 [네이티브 이미지 생성기 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 유틸리티입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
