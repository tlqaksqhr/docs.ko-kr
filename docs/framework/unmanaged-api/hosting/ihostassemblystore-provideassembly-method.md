---
title: IHostAssemblyStore::ProvideAssembly 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32d48931177a42dd14092b4052370764a217abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly 메서드
참조 되지 않은 어셈블리에 대 한 참조는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 반환 되는 [ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)합니다. 공용 언어 런타임 (CLR) 호출 `ProvideAssembly` 목록에 표시 되지 않는 각 어셈블리에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBindInfo`  
 [in] 에 대 한 포인터는 [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) 인스턴스 버전 관리 정책의 유무를 포함 하 여 특정 바인딩 특성을 결정 하는 호스트를 사용 하 고 바인딩할 어셈블리입니다.  
  
 `pAssemblyId`  
 [out] 이 요청된 된 어셈블리에 대 한 고유 식별자에 대 한 포인터 `IStream`합니다.  
  
 `pHostContext`  
 [out] 플랫폼의 필요 없이 요청된 된 어셈블리의 증명 정보를 확인 하는 데 사용 되는 호스트 별로 데이터에 대 한 포인터를 호출 합니다. `pHostContext` 에 해당 하는 <xref:System.Reflection.Assembly.HostContext%2A> 관리 되는 속성 <xref:System.Reflection.Assembly> 클래스입니다.  
  
 `ppStmAssemblyImage`  
 [out] 주소에 대 한 포인터는 `IStream` 이식 가능한 실행 (PE) 이미지를 로드할 수 또는 어셈블리를 찾을 수 없는 경우 null을 포함 하 합니다.  
  
 `ppStmPDB`  
 [out] 주소에 대 한 포인터는 `IStream` 프로그램 디버그 (PDB) 정보 또는 null을 포함 하는.pdb 파일을 찾을 수 없는 경우.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|COR_E_FILENOTFOUND (0X80070002)|요청된 된 어셈블리를 찾을 수 없습니다.|  
|E_NOT_SUFFICIENT_BUFFER|지정 된 버퍼 크기가 `pAssemblyId` 를 반환 하는 호스트의 식별자를 보유할 만큼 크지 않습니다.|  
  
## <a name="remarks"></a>설명  
 Id 값에 대해 반환 `pAssemblyId` 호스트에 의해 지정 됩니다. 식별자는 프로세스의 수명 동안 내에서 고유 해야 합니다. CLR이이 값을 스트림에 대 한 고유 식별자로 사용 합니다. 각 값에 대 한 값에 대해 확인 `pAssemblyId` 에 대 한 다른 호출에서 반환 된 `ProvideAssembly`합니다. 동일한 호스트 반환 `pAssemblyId` 다른 값 `IStream`, CLR 해당 스트림의 내용을 이미 매핑 여부를 확인 합니다. 이 경우 런타임은 새 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
