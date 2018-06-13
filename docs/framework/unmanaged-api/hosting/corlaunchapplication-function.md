---
title: CorLaunchApplication 함수
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a53b0a9cdcec33846f9d491e7d6567bcf9235b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428764"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication 함수
지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에 있는 응용 프로그램을 시작 합니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwClickOnceHost`  
 [in] 값은 [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) 응용 프로그램을 시작 하는 호스트의 형식을 지정 하는 열거형입니다.  
  
 `pwzAppFullName`  
 [in] 실행 하는 응용 프로그램의 전체 이름입니다.  
  
 `dwManifestPaths`  
 [in] 응용 프로그램에 대 한 매니페스트 경로 수를 지정 합니다.  
  
 `ppwzManifestPaths`  
 [in] 경로 실행 하는 응용 프로그램에 대 한 매니페스트를 지정 하며 각 문자열의 배열입니다.  
  
 `dwActivationData`  
 [in] 실행 하는 응용 프로그램에 대 한 정품 인증 데이터 항목의 수입니다.  
  
 `ppwzActivationData`  
 [in] 각각이 실행 하는 응용 프로그램에 대 한 정품 인증 데이터 항목이 문자열의 배열입니다.  
  
 `lpProcessInformation`  
 [out] 응용 프로그램을 로드 하는 프로세스에 대 한 정보에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
