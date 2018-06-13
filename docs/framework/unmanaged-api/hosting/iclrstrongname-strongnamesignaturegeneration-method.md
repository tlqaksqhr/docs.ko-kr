---
title: ICLRStrongName::StrongNameSignatureGeneration 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 217b54a615d7c553e714ef87b3c2bb6a1919ae98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435377"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration 메서드
지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameSignatureGeneration (   
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
  
 경우 `ppbSignatureBlob` 은 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다. 호출자에 게 사용 하 여이 공간을 해제 해야 합니다는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.  
  
 `pcbSignatureBlob`  
 [out] 반환 된 서명의 바이트 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="remarks"></a>설명  
 Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명 크기를 계산 하 합니다.  
  
 서명을 수 파일에 직접 저장 하거나 또는 호출자에 게 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameSignatureGenerationEx 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
