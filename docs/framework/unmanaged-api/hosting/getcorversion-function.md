---
title: "GetCORVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORVersion
helpviewer_keywords: GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6218714030892531f3b9ed4b4a79917347d250db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="getcorversion-function"></a>GetCORVersion 함수
현재 프로세스에서 실행 중인 공용 언어 런타임 (CLR)의 버전 번호를 반환 합니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbuffer`  
 CLR에서 현재 프로세스에 로드 된 런타임 버전을 지정 하는 문자열을 반환 하는 버퍼에 대 한 포인터입니다. 반환 된 문자열은 동일한 형식 문자열에 전달 된 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), 예를 들어 "v1.0.1216"입니다. 런타임 프로세스에 아직 로드 되지 않았습니다 고 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.  
  
 `cchBuffer`  
 문자 수 (`WCHAR`s)에 저장할 수 있는 `pbuffer`합니다.  
  
 `dwLength`  
 에 실제로 반환 된 문자 수에 대 한 포인터 `pbuffer`합니다. 경우 `pbuffer` 가 null 포인터 이면 런타임은 E_POINTER를 반환 합니다. 문자 수가 큰 경우의 길이 `pbuffer` , 런타임은 ERROR_INSUFFICIENT_BUFFER를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
