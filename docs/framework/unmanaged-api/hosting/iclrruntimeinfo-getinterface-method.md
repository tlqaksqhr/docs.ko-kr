---
title: "ICLRRuntimeInfo::GetInterface 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c5150a10a813da85fc035c7bfa43a7647fac308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a>ICLRRuntimeInfo::GetInterface 메서드
현재 프로세스에 CLR을 로드 하 고 런타임 인터페이스 포인터와 같은 반환 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), 및 [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)합니다.  
  
 이 메서드를 모두 대체는 `CorBindTo`*의 함수는 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 섹션.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 [in] Coclass에 대 한 CLSID 인터페이스입니다.  
  
 `riid`  
 [in] 요청 된 IID `rclsid` 인터페이스입니다.  
  
 `ppUnk`  
 [out] 쿼리 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`ppUnk`가 null인 경우|  
|E_OUTOFMEMORY|요청을 처리할 메모리가 부족 합니다.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|각기 다른 런타임 레거시 CLR 버전 2 정품 인증 정책에 이미 바인딩 되었습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하면 CLR 로드 되지만 초기화 되지 않았습니다.  
  
 다음 표에서 지원 되는 조합을 `rclsid` 및 `riid`합니다.  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CorMetaDataDispenser|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorMetaDataDispenserRuntime|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorRuntimeHost|IID_ICorRuntimeHost|  
|CLSID_CLRRuntimeHost|IID_ICLRRuntimeHost|  
|CLSID_TypeNameFactory|IID_ITypeNameFactory|  
|CLSID_CLRDebuggingLegacy|IID_ICorDebug|  
|||  
|CLSID_CLRStrongName|IID_ICLRStrongName|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRRuntimeInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
