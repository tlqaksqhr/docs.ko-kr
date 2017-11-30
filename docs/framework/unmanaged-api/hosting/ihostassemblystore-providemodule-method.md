---
title: "IHostAssemblyStore::ProvideModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6894d15221b8ace12e76b8eba4ac69503eaa792d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule 메서드
어셈블리 또는 연결 된 (그러나 포함이 아님) 내의 모듈 리소스 파일을 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBindInfo`  
 [in] 에 대 한 포인터는 [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 요청된 된 모듈을 나타내는 인스턴스 <xref:System.AppDomain>, 어셈블리 및 모듈 이름입니다.  
  
 `pdwModuleId`  
 [out] 에 대 한 고유 식별자에 대 한 포인터는 `IStream` 로드 된 모듈을 포함 합니다.  
  
 `ppStmModuleImage`  
 [out] 주소에 대 한 포인터는 `IStream` 이식 가능한 실행 (PE) 이미지를 로드할 수를 포함 된 개체 또는 모듈을 찾을 수 없는 경우 null입니다.  
  
 `ppStmPDB`  
 [out] 주소에 대 한 포인터는 `IStream` 또는 개체 요청된 된 모듈에 대 한 프로그램 (PDB) 디버그 정보를 포함 하는.pdb 파일을 찾을 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ProvideModule`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|COR_E_FILENOTFOUND (0X80070002)|요청한 어셈블리 또는 링크 된 리소스를 찾을 수 없습니다.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId`호스트를 반환 하는 식별자를 포함할 수 없는 경우|  
  
## <a name="remarks"></a>설명  
 Id 값에 대해 반환 `pdwModuleId` 호스트에 의해 지정 됩니다. 식별자는 프로세스의 수명 동안 내에서 고유 해야 합니다. CLR에서이 값을 연결 된 스트림 고유 식별자로 사용 합니다. 각 값에 대 한 값에 대해 확인 `pAssemblyId` 에 대 한 호출에서 반환 된 [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 및에 대 한 값과 대조 `pdwModuleId` 에 대 한 다른 호출에서 반환 된 `ProvideModule`합니다. 호스트가 다른 같은 식별자 값을 반환 하는 경우 `IStream`, CLR 해당 스트림의 내용을 이미 매핑 여부를 확인 합니다. 이 경우 CLR 새 매핑하는 대신 이미지의 기존 복사본을 로드 합니다. 따라서 식별자도 겹치지 않아야에서 반환 된 어셈블리 식별자와 `ProvideAssembly`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
