---
title: RUNTIME_INFO_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e544db23abf89a20bd2f7763cfdb1256ea4a326c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441366"
---
# <a name="runtimeinfoflags-enumeration"></a>RUNTIME_INFO_FLAGS 열거형
공용 언어 런타임 (CLR)에 대 한 정보를 반환 하는지를 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|디렉터리 정보를 포함 하지 않아야 있는지 나타냅니다.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|버전 정보를 포함 하지 않아야 있는지 나타냅니다.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|실패 시 오류 대화 상자를 표시 되지 않음을 나타냅니다.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|나타냅니다 호출의 효과 [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 플래그로 함수를 재정의 해야 합니다. 즉, 설치 대화 상자가 표시 되지 않고 오류 발생 시 표시 되어야 합니다.|  
|`RUNTIME_INFO_REQUEST_AMD64`|런타임의 AMD 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.|  
|`RUNTIME_INFO_REQUEST_IA64`|런타임의 IA 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.|  
|`RUNTIME_INFO_REQUEST_X86`|런타임의 x86 호환 버전에 대 한 정보에 대 한 요청을 나타냅니다.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|버전 업그레이드 정보를 포함 해야 함을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 다음 플랫폼 아키텍처 플래그 한 번에 하나만 지정된 될 수 있습니다 및 함께 사용할 수 없습니다.  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
