---
title: "COR_PRF_JIT_CACHE 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_JIT_CACHE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_JIT_CACHE
helpviewer_keywords: COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5041e12c6745d43518ee2ac45e3a0a79c1c50ca3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfjitcache-enumeration"></a>COR_PRF_JIT_CACHE 열거형
캐시된 함수 검색의 결과를 나타냅니다.  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND`값이 0 높으므로 `COR_PRF_JIT_CACHE` 를 부울 대신 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|검색 함수를 찾을 수 있습니다.|  
|`COR_PRF_FUNCTION_NOT_FOUND`|검색 함수를 찾지 못했습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
