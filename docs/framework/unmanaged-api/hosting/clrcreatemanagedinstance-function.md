---
title: "ClrCreateManagedInstance 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: ClrCreateManagedInstance
helpviewer_keywords: ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d27a881f84121f0d096eae7c693dec5b674caec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 함수
지정 된 관리 되는 형식의 인스턴스를 만듭니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 관리 되는 형식의 인스턴스를 만드는 COM 정품 인증을 사용 하거나 호스팅을 사용 (참조 [CLR 호스팅 인터페이스에 추가 된.NET Framework 4 및 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pTypeName`  
 [in] 요청 되는 인스턴스 형식 이름에 대 한 포인터입니다.  
  
 `riid`  
 [in] `IID` 요청 되는 인스턴스 형식입니다.  
  
 `ppObject`  
 [out] 호출자에 의해 요청 된 관리 되는 형식의 인스턴스로에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 공용 언어 런타임 프로세스에 이미 로드 해야 합니다. 예를 들어에 대 한 호출을 사용 하 여 로드할 수 있습니다는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하기 전에 함수는 `ClrCreateManagedInstance` 함수를 호출 합니다. 런타임이 로드 되지 않은 경우 `ClrCreateManagedInstance` 먼저 런타임 v 1.0.3705를 로드 하려고 합니다. 실패할 경우 최신 버전의 런타임 로드를 시도 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
