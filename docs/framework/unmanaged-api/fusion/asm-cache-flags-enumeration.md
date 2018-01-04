---
title: "ASM_CACHE_FLAGS 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASM_CACHE_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: ASM_CACHE_FLAGS
helpviewer_keywords: ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87dce9a2daf7067409d78a9f389695b6b01f23c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="asmcacheflags-enumeration"></a>ASM_CACHE_FLAGS 열거형
나타내는 어셈블리의 소스를 나타냅니다 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) 전역 어셈블리 캐시에 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Ngen.exe를 사용 하 여 미리 컴파일된 어셈블리의 캐시를 열거 합니다.|  
|`ASM_CACHE_GAC`|전역 어셈블리 캐시를 열거합니다.|  
|`ASM_CACHE_DOWNLOAD`|필요에 따라 다운로드 된 또는 섀도 복사 된 어셈블리를 열거 합니다.|  
|`ASM_CACHE_ROOT`|나타냅니다는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) 함수 공용 언어 런타임 (CLR) 버전 2.0에 대 한 전역 어셈블리 캐시에 경로 반환 해야 합니다. 에 대 한 호출의 경우에만 의미 있는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)합니다.|  
|`ASM_CACHE_ROOT_EX`|나타냅니다는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) 함수 CLR 버전 4에 대 한 전역 어셈블리 캐시에 경로 반환 해야 합니다. 에 대 한 호출의 경우에만 의미 있는 [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetCachePath 함수](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [IAssemblyCacheItem 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
