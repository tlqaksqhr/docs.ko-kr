---
title: ICLRMetaHost::RequestRuntimeLoadedNotification 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ac041db64a874cc143657c601f30e4482dd2462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434437"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification 메서드
공용 언어 런타임 (CLR) 버전은 처음 로드 되었지만 아직 시작 되지 않았을 때 호출 될 보장 되는 콜백 함수를 제공 합니다. 이 메서드를 대체는 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallbackFunction`  
 [in] 에서는 새로운 런타임 로드 되었을 때 호출 되는 콜백 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pCallbackFunction`가 null인 경우|  
  
## <a name="remarks"></a>설명  
 콜백은 다음과 같은 방식으로 작동합니다.  
  
-   런타임을 처음으로 로드 되는 경우에는 콜백이 호출 됩니다.  
  
-   같은 런타임 재진입 로드에 대 한 콜백을 호출 되지 않습니다.  
  
-   재진입 런타임 로드에 대 한 콜백 함수 호출에 serialize 됩니다.  
  
 콜백 함수에는 다음과 같은 프로토타입이 있습니다.  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 콜백 함수 프로토타입에 다음과 같습니다.  
  
-   `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 호스트가를 로드 하거나 다른 런타임을 재진입 방식으로 로드 되도록 하는 경우는 `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 콜백에서 함수는 다음과 같이 사용 해야 하는 제공 되는 매개 변수:  
  
-   `pfnCallbackThreadSet` 로드를 시도 되기 전에 런타임 부하를 일으킬 수 있는 스레드에서 호출 되어야 합니다.  
  
-   `pfnCallbackThreadUnset` 스레드가 더 이상 이러한 런타임 로드 될 때 (및 초기 콜백에서 반환 하기 전에) 호출 되어야 합니다.  
  
-   `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 재진입은 모두입니다.  
  
> [!NOTE]
>  호스트 응용 프로그램 호출 해서는 안 `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 범위 밖에 서는 `pCallbackFunction` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRMetaHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
