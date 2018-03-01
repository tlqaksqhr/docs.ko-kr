---
title: "PublicKeyBlob 구조체"
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
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1f04c692b7549c4d7d8d431591eeb867b673d9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob 구조체
공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`SigAlgId`|서명 알고리즘에 대 한 식별자 (형식의 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.|  
|`HashAlgId`|해시 알고리즘에 대 한 식별자 (형식의 `ALG_ID`WinCrypt.h에 정의 된 대로) 공개 키입니다.|  
|`cbPublicKey`|바이트의 키 길이입니다.|  
|`PublicKey`|CryptoAPI에 의해 반환 되는 형식과의 키 값을 포함 하는 가변 길이 바이트 배열입니다.|  
  
## <a name="remarks"></a>설명  
 `PublicKeyBlob` 구조체를 사용 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), 및를 공개/개인 키 쌍의 공개 키를 나타내는 다른 강력한 이름의 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameGetPublicKey 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [StrongNameSignatureGeneration 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [강력한 이름 지정 구조체](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
