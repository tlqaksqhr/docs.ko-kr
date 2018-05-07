---
title: EMemoryCriticalLevel 열거형
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf4f3f582e417c5e7b814622986427f996796ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel 열거형
특정 메모리 할당이 요청 되었으나 처리할 수 없는 경우 오류가 끼치는 영향을 표시 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAppDomainCritical`|할당 된 할당에서 요청한 도메인의 관리 되는 코드 실행에 대 한 중요 한 임을 나타냅니다. 메모리를 할당할 수 없으면 CLR 도메인을 보장할 수 없습니다. 호스트에 할당할 수 없는 경우 수행할 작업을 결정 합니다. 중단 하는 CLR에 지시할 수 있습니다는 `AppDomain` 자동으로 하거나에서 메서드를 호출 하 여 계속 해 서 실행을 허용할 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)합니다.|  
|`eProcessCritical`|할당 프로세스에서 관리 코드의 실행에 매우 중요 함을 나타냅니다. 이 값은 종료자를 실행할 때 시작 하는 동안 사용 됩니다. 메모리를 할당할 수 없으면 CLR 프로세스에서 사용할 수 없습니다. 할당이 실패 하면 CLR 효과적으로 사용할 수 없습니다. 모든 후속 호출을 CLR HOST_E_CLRNOTAVAILABLE 실패합니다.|  
|`eTaskCritical`|할당 작업 할당 요청을 실행 하려면 반드시 함을 나타냅니다. 메모리를 할당할 수 없으면 CLR 태스크가 실행 될 수 있도록 보장할 수 없습니다. CLR 장애가 발생 한 <xref:System.Threading.ThreadAbortException> 실제 운영 체제 스레드에서에 합니다.|  
  
## <a name="remarks"></a>설명  
 에 정의 된 메모리 할당 메서드는 [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) 및 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인터페이스는이 형식의 매개 변수를 사용 합니다. 오류의 심각도에 따라, 호스트 여부를 결정할 수 즉시 할당 요청에 실패 하거나 수 충족 될 때까지 기다려야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRMemoryNotificationCallback 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
