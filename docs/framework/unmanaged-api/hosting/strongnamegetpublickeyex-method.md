---
title: "StrongNameGetPublicKeyEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameGetPublicKeyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e94498cc8841a95e1918d3f26bd19256793564ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx 메서드
공개/개인 키 쌍에서 공개 키를 가져옵니다 하 고는 해시 알고리즘 및 서명 알고리즘을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzKeyContainer`  
 [in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다. 경우 `pbKeyBlob` 매개 변수가 null 이면 `szKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다. 이 경우에 `StrongNameGetPublicKeyEx` 메서드 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.  
  
 경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.  
  
 키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다. 다른 형식의 키이 이번에 사용할 수 있습니다.  
  
 `pbKeyBlob`  
 [in] 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다. 경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.  
  
 `cbKeyBlob`  
 [in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.  
  
 `ppbPublicKeyBlob`  
 [out] 반환 된 공개 키 BLOB입니다. `ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다. 호출자에 게 사용 하 여 메모리를 해제 해야는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.  
  
 `pcbPublicKeyBlob`  
 [out] 반환 된 공개 키 BLOB의 크기입니다.  
  
 `uHashAlgId`  
 [in] 어셈블리 해시 알고리즘입니다. 허용 되는 값의 목록은 설명 섹션을 참조 하십시오.  
  
 `uReserved`  
 [in] 나중에 사용 됩니다. 기본값은 null입니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="remarks"></a>설명  
 공개 키에 포함 된 한 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 허용 되는 값에 대 한 집합을 보여 줍니다.는 `uHashAlgId` 매개 변수입니다.  
  
|name|값|  
|----------|-----------|  
|없음|0|  
|S H A-1|0x8004|  
|S H A-256|0x800c|  
|S H A-384|0x800d|  
|S H A-512|0x800e|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameTokenFromPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob 구조체](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [StrongNameGetPublicKey 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
