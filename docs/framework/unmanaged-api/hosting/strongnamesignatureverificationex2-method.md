---
title: "StrongNameSignatureVerificationEx2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4faa7fee32d9cab5a75772f29d2014473e2bee0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2 메서드
강력한 이름의 어셈블리의 서명을 확인 하 고 실제 키를 ECMA 키로의 매핑을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 이식 가능한 실행 (.exe 또는.dll) 파일에 어셈블리를 확인할 수에 대 한 경로입니다.  
  
 `fForceVerification`  
 [in] `true` 고, 그렇지 않으면 레지스트리 설정을 재정의 하는 데 필요한 경우에 유효성 검사를 수행 하려면 `false`합니다.  
  
 `pbEcmaPublicKey`  
 [in] 확인에 사용 된 실제 키를 ECMA 공개 키에서 매핑에 대 한 포인터입니다.  
  
 `cbEcmaPublicKey`  
 [in] 실제 ECMA 공개 키의 길이입니다.  
  
 `pfWasVerified`  
 [out] `true` 강력한 이름 서명을 했으면 확인 된, `false`합니다. 이 매개 변수는 또한 설정 `false` 레지스트리 설정으로 인해 확인 되 면 합니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`확인에 성공 하면 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameSignatureVerification 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [StrongNameSignatureVerificationEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
