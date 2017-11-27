---
title: "IHostMemoryManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager 인터페이스
표준 Win32 가상 메모리 함수를 사용 하는 대신 공용 언어 런타임 (CLR)에서 호스트를 통해 가상 메모리를 요청을 허용 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|공용 언어 런타임 (CLR)가 운영 체제에서 지정된 된 메모리를 확보 되었음을 호스트에 알립니다.|  
|[CreateMAlloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|한 인터페이스 포인터를 가져옵니다는 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 힙을 호스트에서 만든 메모리 할당을 요청 하는 데 사용 되는 인스턴스.|  
|[GetMemoryLoad 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|호스트에 의해 보고 현재 사용 중인 실제 메모리의 양을 가져옵니다.|  
|[NeedsVirtualAddressSpace 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|CLR이 지정 된 메모리 사용을 시도 하려는 호스트에 알립니다.|  
|[RegisterMemoryNotificationCallback 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|호스트의 컴퓨터에서 현재 메모리 사용량 CLR에 알리기 위해 호출 하는 콜백 함수에 대 한 포인터를 등록 합니다.|  
|[ReleasedVirtualAddressSpace 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|CLR에서 지정 된 메모리를 사용 하 여 완료 되었음을 호스트에 알립니다.|  
|[VirtualAlloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|예약 하거나 호출 프로세스의 가상 주소 공간에 있는 페이지의 영역을 커밋합니다 해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다.|  
|[VirtualFree 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|해당 Win32 함수, 해제, 커밋 또는 해제 하 고는 호출 프로세스의 가상 주소 공간 내에 있는 페이지의 영역을 커밋에 대 한 논리 래퍼 역할을 합니다.|  
|[VirtualProtect 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|호출 프로세스의 가상 주소 공간에서 커밋된 페이지의 영역에 대해 보호를 변경 하는 해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다.|  
|[VirtualQuery 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|호출 프로세스의 가상 주소 공간에 있는 페이지의 범위에 대 한 정보를 검색 하는 해당 Win32 함수에 대 한 논리적 래퍼입니다로 사용 됩니다.|  
  
## <a name="remarks"></a>설명  
 `IHostMemoryManager`또한 호스트에 의해 보고 되는 힙에서 메모리를 요청 하 고 프로세스의 메모리 압력 수준의 얻을 대 한 포인터를 가져오는를 CLR에 대 한 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
