---
title: LoadLibraryShim 함수
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8936fa3d22cfde4c2536fccf9d46c1990133db1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim 함수
지정 된 버전의.NET Framework 재배포 가능 패키지에 포함 된 DLL 로드 합니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 사용 하 여 [iclrruntimeinfo:: Loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szDllName`  
 [in] .NET Framework 라이브러리를 로드할 수 있는 DLL의 이름을 나타내는 0으로 끝나는 문자열입니다.  
  
 `szVersion`  
 [in] DLL 로드의 버전을 나타내는 0으로 끝나는 문자열입니다. 경우 `szVersion` 가 null 이면 로드를 버전 4 보다 작은 지정된 된 DLL의 최신 버전에 대해 선택한 버전입니다. 즉, 버전 4 보다 크거나 같은 모든 버전 경우 무시 됩니다 `szVersion` 매개 변수가 null 이면 및 없는 버전 보다 작은 버전 4가 설치 되어 DLL 로드 되지 않습니다. 이의 설치 프로그램을 확인 하기는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 기존 응용 프로그램 또는 구성 요소에는 영향을 주지 않습니다. 항목을 참조 [In-proc SxS 및 마이그레이션 빠른 시작](http://go.microsoft.com/fwlink/?LinkId=200329) CLR 팀 블로그에서.  
  
 `pvReserved`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `phModDll`  
 [out] 모듈의 핸들에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|CLR_E_SHIM_RUNTIMELOAD|로드 `szDllName` 공용 언어 런타임 (CLR) 및 CLR의 필수 버전을 로드할 수 없습니다 로드 해야 합니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는.NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 하려고 사용 됩니다. 사용자가 생성 한 Dll은 로드 되지 않습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0 부터는 Fusion.dll 로드 하면 CLR이 로드 되도록 합니다. Fusion.dll 함수는 런타임에 의해 구현을 제공 하는 래퍼 이지만 이제 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
