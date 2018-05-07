---
title: EApiCategories 열거형
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="eapicategories-enumeration"></a>EApiCategories 열거형
부분적으로 신뢰할 수 있는 코드에서 실행 되는 호스트를 차단할 수 있는 기능의 범주를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAll`|모든 다른 검사는 클래스와 멤버 관리 지정 `EApiCategories` 필드 부분적으로 신뢰할 수 있는 코드에서 실행 차단 합니다.|  
|`eExternalProcessMgmt`|관리 되는 클래스 및 멤버 만들기, 조작, 외부 프로세스의 소멸을 수행할 수 있는 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eExternalThreading`|관리 되는 클래스 및 멤버 만들기, 조작, 외부 스레드의 소멸을 수행할 수 있는 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eMayLeakOnAbort`|부분적으로 신뢰할 수 있는 코드에서 실행 중단 시 메모리 누수가 발생할 수 있는 관리 되는 형식 및 멤버 차단 하도록 지정 합니다.|  
|`eNoCategory`|관리 코드 범주가 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eSecurityInfrastructure`|공용 언어 런타임 (CLR) 보안 인프라에서 부분적으로 신뢰할 수 있는 코드에서 사용 하 고 차단 하도록 지정 합니다.|  
|`eSelfAffectingProcessMgmt`|관리 되는 클래스 및 멤버 호스팅된 프로세스 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eSelfAffectingThreading`|관리 되는 클래스 및 멤버 호스팅된 프로세스의 스레드가 영향을 줄 수 있는 기능이 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eSharedState`|공유 상태를 노출 하는 관리 되는 클래스와 멤버 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eSynchronization`|공용 언어 런타임 클래스 및 멤버를 잠금을 유지 하는 사용자 코드를 사용 하면 부분적으로 신뢰할 수 있는 코드에서 실행 차단 하도록 지정 합니다.|  
|`eUI`|부분적으로 신뢰할 수 있는 코드에서 실행을 허용 하거나 사용자 상호 작용을 요청 하는 관리 되는 클래스와 멤버 차단 하도록 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 [iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) 형식의 매개 변수를 사용 하는 메서드 `EApiCategories`합니다.  
  
 `EApiCategories` 열거형 및 `SetProtectedCategories` 메서드 직접 관련 된 관리 되는 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 클래스입니다. 관리 되는 클래스와 함께 사용 되는 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 해당 값에 직접 해당 열거형의 `EApiCategories` 관리 되는 형식 및 해당 범주에서 설명 하는 기능을 노출 하는 멤버를 표시 하려면 값 `EApiCategories`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRHostProtectionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
