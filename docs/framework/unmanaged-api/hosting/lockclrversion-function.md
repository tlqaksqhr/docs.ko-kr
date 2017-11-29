---
title: "LockClrVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be41ae47f78a41e2f2be10a1e38d938dde9a4701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lockclrversion-function"></a>LockClrVersion 함수
호스트가 명시적으로 CLR을 초기화 하기 전에 프로세스에서 사용할 공용 언어 런타임 (CLR)의 버전은 결정할 수 있습니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hostCallback`  
 [in] 초기화 시 CLR에서 호출 되는 함수입니다.  
  
 `pBeginHostSetup`  
 [in] 해당 초기화 CLR 알리기 위해 호스트에 의해 호출 될 함수를 시작 합니다.  
  
 `pEndHostSetup`  
 [in] 호출할 함수를 CLR 알리기 위해 호스트에 의해 초기화 완료 되었습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|인수 중 하나 이상이 null입니다.|  
  
## <a name="remarks"></a>설명  
 호스트에서는 `LockClrVersion` CLR을 초기화 하기 전에. `LockClrVersion`모두 형식의 콜백을 세 개의 매개 변수 [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)합니다. 이 형식은 다음과 같이 정의 됩니다.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 다음 단계는 런타임 초기화할 때 발생합니다.  
  
1.  호스트에서는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 다른 런타임 초기화 함수 중 하나입니다. 또는 호스트 COM 개체 활성화를 사용 하 여 런타임을 초기화할 합니다.  
  
2.  런타임에서 호출 하 여 지정 된 함수는 `hostCallback` 매개 변수입니다.  
  
3.  지정 된 함수의 `hostCallback` 다음과 같은 호출 시퀀스를 사용 하는 합니다.  
  
    -   에 지정 된 함수는 `pBeginHostSetup` 매개 변수입니다.  
  
    -   `CorBindToRuntimeEx`(또는 다른 런타임 초기화 함수)입니다.  
  
    -   [Iclrruntimehost:: Sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)합니다.  
  
    -   [Iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)합니다.  
  
    -   에 지정 된 함수는 `pEndHostSetup` 매개 변수입니다.  
  
 로부터의 모든 호출은 `pBeginHostSetup` 를 `pEndHostSetup` 단일 스레드 또는 파이버 동일한 논리 스택에서 수행 되어야 합니다. 이 스레드는 스레드가 서로 다를 수 `hostCallback` 라고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
