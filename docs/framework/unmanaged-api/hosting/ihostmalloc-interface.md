---
title: "IHostMalloc 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a>IHostMalloc 인터페이스
공용 언어 런타임 (CLR)에서 호스트를 통해 힙의 세분화 된 할당을 요청을 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Alloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|호스트 힙에서 요청된 된 양의 메모리를 할당 하는 요청 수입니다.|  
|[DebugAlloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|호스트는 힙의 요청 된 양의 메모리를 할당 하 고 추가로 메모리 할당 된 추적 요청 합니다.|  
|[Free 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|사용 하 여 할당 된 메모리를 해제는 `Alloc` 메서드.|  
  
## <a name="remarks"></a>설명  
 CLR에 대 한 인터페이스 포인터를 가져옵니다는 `IHostMalloc` 호출 하 여 인스턴스는 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
