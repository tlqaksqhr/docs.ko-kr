---
title: ECustomDumpFlavor 열거형
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6d0ba3f722f63650a3db6a8f633189993db0716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431410"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor 열거형
힙 사용자 정의 하위 집합에 포함할 항목을 덤프 오류를 보고할 때 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|사용자 지정 힙 덤프 미니 덤프로 시작 하 고 지정한 추가 데이터를 포함 하는지 지정 [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 인스턴스를 같은 메서드에 전달 합니다.|  
|`DUMP_FLAVOR_NonHeapCLRState`|사용자 지정 힙 덤프가 동적으로 할당 되지 않은 모든 런타임 상태 데이터를 수집 해야 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 형식의 매개 변수 `ECustomDumpFlavor` 에 전달 되는 [iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ECustomDumpItemKind 열거형](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [ICLRErrorReportingManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
