---
title: CertVerifyAuthenticodeLicense 함수
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d79a8c5bc204b6479741c32c47e6b41ff873a1bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406925"
---
# <a name="certverifyauthenticodelicense-function"></a>CertVerifyAuthenticodeLicense 함수
Authenticode XrML 라이선스의 유효성을 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pLicenseBlob`  
 [in] 확인할 Authenticode XrML 라이선스입니다.  
  
 참조는 [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) 구조입니다.  
  
 `dwFlags`  
 [in] 선택적 항목으로, 다음 값의 조합입니다.  
  
-   AXL_REVOCATION_NO_CHECK  
  
-   AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
-   AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
-   AXL_URL_CACHE_ONLY_RETRIEVAL  
  
-   AXL_LIFETIME_SIGNING  
  
-   AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [out] 서명자의 정보를 받는 데 사용되는 매개 변수입니다. 라이선스가 서명되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다. 사용 하 여 리소스를 해제 해야 하는 호출자의는 [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) 함수 후 사용 합니다.  
  
 참조 [AXL_AUTHENTICODE_SIGNER_INFO 구조](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)합니다.  
  
 `pTimestamperInfo`  
 [out] 타임스탬퍼 정보(있는 경우)를 받으려는 경우 설정합니다. 라이선스에 타임스탬프가 적용되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다. 사용 하 여 리소스를 해제 해야 하는 호출자의는 [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) 함수 후 사용 합니다.  
  
 참조 [AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `S_OK`가 반환됩니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [GetHashFromHandle 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
