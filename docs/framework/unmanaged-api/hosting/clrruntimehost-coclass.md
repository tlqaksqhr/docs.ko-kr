---
title: CLRRuntimeHost Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost Coclass
런타임에 의해 코드 실행을 관리 하기 위한 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|[ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|런타임에서 응용 프로그램의 실행을 제어 하기 위한 메서드를 제공 합니다.|  
|[ICLRValidator 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|유효성 검사 오류를 자세히 보고에 대 한 메서드 이식 가능한 실행 이미지의 유효성 검사에 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 Coclass](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
