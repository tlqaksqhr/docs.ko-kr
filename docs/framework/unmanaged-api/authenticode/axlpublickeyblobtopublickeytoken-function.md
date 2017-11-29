---
title: "_AxlPublicKeyBlobToPublicKeyToken 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlPublicKeyBlobToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25a6a78fad95b894e82a75159458f25264f0ee0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>_AxlPublicKeyBlobToPublicKeyToken 함수
CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCspPublicKeyBlob`  
 [in] CSP 공개 키 Blob입니다.  
  
 `ppwszPublicKeyHash`  
 [out] 16진수로 인코딩된 공개 키 해시를 받는 WCHAR *에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 함수가 정상적으로 실행되는 경우 `S_OK`이고 그러지 않으면 `S_FALSE`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
