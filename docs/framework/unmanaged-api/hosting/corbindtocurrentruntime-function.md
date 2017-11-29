---
title: "CorBindToCurrentRuntime 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: HeaderDef
f1_keywords: CorBindToCurrentRuntime
helpviewer_keywords: CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 630dab4fec8c37bd776b68870a53ab20e4050e06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime 함수
XML 파일에 저장 된 버전 정보를 사용 하 여 공용 언어 런타임 (CLR) 프로세스를 로드 합니다. XML 파일의 형식은 표준 응용 프로그램 구성 파일에 모델링 됩니다. 구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 참조 [공용 언어 런타임 프로세스에 로드](http://msdn.microsoft.com/en-us/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwszFileName`  
 [in] 로드 하기 위해 CLR의 버전을 지정 하는 응용 프로그램 구성 파일의 이름입니다. 파일 이름이 정규화 된 디렉터리가 아닙니다 전화 통화를 걸기 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.  
  
 로드할 런타임 버전을 version 특성에 의해 설명 된 [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 구성 파일의 요소입니다.  
  
 버전이 지정 되지, 아니면는 `<requiredRuntime>` 요소를 찾을 수 없습니다, 최신 버전의 컴퓨터에 설치 된 CLR 로드 됩니다.  
  
 `rclsid`  
 [in] `CLSID` 중 하나를 구현 하는 coclass의는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다. 지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.  
  
 `riid`  
 [in] `IID` 요청 하는 인터페이스입니다. 지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.  
  
 `ppv`  
 [out] 반환 된 인터페이스 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CorBindToRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
