---
title: "IHostIoCompletionManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager
helpviewer_keywords: IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 847d4c3aa3e3da94b4aac4679ada047577379f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager 인터페이스
공용 언어 런타임 (CLR) 호스트에서 제공 하는 I/O 완료 포트와 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Bind 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|I/O 완료 포트에 대 한 핸들을 바인딩합니다.|  
|[CloseIoCompletionPort 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|에 대 한 이전 호출을 통해 생성 된 포트를 닫고 `CreateIoCompletionPort`합니다.|  
|[CreateIoCompletionPort 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|요청 호스트 새 I/O 완료 포트를 만듭니다.|  
|[GetAvailableThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|현재 요청을 처리 하지는 I/O 완료 스레드 수를 가져옵니다.|  
|[GetHostOverlappedSize 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|호스트에서 I/O 요청에 추가 하려는 사용자 지정 데이터의 크기를 가져옵니다.|  
|[GetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|I/O 요청을 처리 하는 호스트를 할당할 수 있는 스레드 최대 수를 가져옵니다.|  
|[GetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|I/o 호스트에서 제공 하는 스레드의 최소 수를 가져옵니다.|  
|[InitializeHostOverlapped 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|I/O 요청에 대 한 사용자 지정 데이터를 초기화할 수 있는 호스트를 제공 합니다.|  
|[SetCLRIoCompletionManager 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|호스트에 대 한 인터페이스 포인터에 제공 된 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) 인스턴스는 CLR에서 구현 합니다.|  
|[SetMaxThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|I/O 요청을 할당 하는 호스트 하는 스레드의 최대 수를 설정 합니다.|  
|[SetMinThreads 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|I/O 완료를 할당할 호스트 하는 스레드의 최소 수를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostIoCompletionManager`에 해당 하는 `ICLRIoCompletionManager` CLR에서 구현 된 인터페이스입니다. 메서드를 호출 하는 CLR `IHostIoCompletionManager` 핸들의 메서드를 호출 하는 호스트 및 호스트를 제공 하는 포트에 바인딩할 `ICLRIoCompletionManager` 입/출력 요청 완료를 보고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
