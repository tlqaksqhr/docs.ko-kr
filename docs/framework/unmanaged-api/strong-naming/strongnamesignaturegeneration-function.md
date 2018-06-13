---
title: StrongNameSignatureGeneration 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0555299779aebc6cc37c3863e8b5504b357b262
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461495"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration 함수
지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 강력한 이름 서명을 생성 될 어셈블리의 매니페스트가 포함 된 파일 경로입니다.  
  
 `wszKeyContainer`  
 [in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.  
  
 경우 `pbKeyBlob` 매개 변수가 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다. 이 경우에 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.  
  
 경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.  
  
 키 서명 키 1024 비트 Rivest-Shamir-Adleman (RSA) 이어야 합니다. 다른 형식의 키이 이번에 사용할 수 있습니다.  
  
 `pbKeyBlob`  
 [in] 공개/개인 키 쌍에 대 한 포인터입니다. 이 쌍은 win32 만든 형식 `CryptExportKey` 함수입니다. 경우 `pbKeyBlob` 가 null 이면에서 지정한 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하는로 간주 됩니다.  
  
 `cbKeyBlob`  
 [in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.  
  
 `ppbSignatureBlob`  
 [out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다. 경우 `ppbSignatureBlob` 가 null 이면 런타임에 서명을 저장 하 여 지정 된 파일에 `wszFilePath`합니다.  
  
 경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다. 호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수입니다.  
  
 `pcbSignatureBlob`  
 [out] 반환 된 서명의 바이트 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.  
  
 서명을 수 파일에 직접 저장 하거나 또는 호출자에 게 반환 합니다.  
  
 경우는 `StrongNameSignatureGeneration` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameSignatureGeneration 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [StrongNameSignatureGenerationEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
