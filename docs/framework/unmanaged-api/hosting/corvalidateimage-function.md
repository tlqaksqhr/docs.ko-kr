---
title: "_CorValidateImage 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidateimage-function"></a>_CorValidateImage 함수
관리 모듈 이미지가 유효성을 검사 하 고 로드 된 후에 운영 체제 로더를에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ImageBase`  
 [in] 관리 되는 코드 유효성을 검사할 이미지의 시작 위치에 대 한 포인터입니다. 이미 이미지를 메모리에 로드 해야 합니다.  
  
 `FileName`  
 [in] 이미지의 파일 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 이 함수는 표준 값 반환 `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, 및 `E_FAIL`, 다음 값 뿐만 아니라 합니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|이미지가 올바르지 않습니다. 이 값은 HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|이미지 유효합니다. 이 값은 HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>설명  
 Windows XP 이상 버전에서 운영 체제 로더는 공용 개체 파일 형식 (COFF) 헤더에 COM 설명자 디렉터리 비트를 검사 하 여 관리 모듈을 확인 합니다. 설정 비트는 관리 모듈을 나타냅니다. MsCorEE.dll 및 호출 로더는 관리 모듈을 감지 하면 로드 `_CorValidateImage`, 다음 작업을 수행 하는 합니다.  
  
-   이미지 유효한 관리 되는 모듈 인지 확인 합니다.  
  
-   공용 언어 런타임 (CLR)의 진입점으로 이미지의 진입점을 변경합니다.  
  
-   64 비트 버전의 Windows에서는 이미지를 p e 32에서 PE32 + 형식으로 변환 하 여 메모리에 있는 이미지를 수정 합니다.  
  
-   관리 모듈 이미지가 로드 될 때 로더를 반환 합니다.  
  
 실행 가능 이미지에 대 한 운영 체제 로더에 다음 호출에서 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 실행 파일에 지정 된 진입점에 관계 없이 함수입니다. 로더가 DLL 어셈블리 이미지에 대 한 호출에서 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수입니다.  
  
 `_CorExeMain`또는 `_CorDllMain` 다음 작업을 수행 합니다.  
  
-   CLR을 초기화합니다.  
  
-   어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다.  
  
-   실행을 시작합니다.  
  
 로더 호출은 [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) 관리 되는 경우에 작동 모듈 이미지가 로드 됩니다. 그러나이 함수 조치; 수행 하지 않습니다. 만 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
