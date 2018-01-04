---
title: "GetCachePath 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: GetCachePath
helpviewer_keywords: GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 371dab83d7441681b9d6bd5723bcd8c3caadb50e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getcachepath-function"></a>GetCachePath 함수
지정된 된 플래그를 사용 하 여 캐시 된 어셈블리에 경로 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCacheFlags`  
 [in] [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 캐시 된 어셈블리의 소스를 나타내는 값입니다.  
  
 `pwzCachePath`  
 [out] 반환 된 포인터의 경로입니다.  
  
 `pcchPath`  
 [out에서] 요청 된 최대 길이 `pwzCachePath`, 및의 실제 길이 반환 시 `pwzCachePath`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ASM_CACHE_FLAGS 열거형](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
