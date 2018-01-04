---
title: "_CorImageUnloading 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f0c105e84d34e83320d6c7d159a94ba4148b302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corimageunloading-function"></a>_CorImageUnloading 함수
관리 모듈 이미지가 로드 때 로더에 알립니다.  
  
 이 함수는 구현 되지 않았습니다. 를 호출 하는 경우 E_NOTIMPL을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ImageBase`  
 [in] 언로드할 이미지의 시작 위치에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
