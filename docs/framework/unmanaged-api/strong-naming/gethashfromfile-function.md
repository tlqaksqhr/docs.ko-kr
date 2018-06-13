---
title: GetHashFromFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98f888280090bfa613acf6ae37bc60ab63c371e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456516"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile 함수
지정된 된 파일의 내용에 대 한 해시를 생성 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szFilePath`  
 [in] 해시 파일의 이름입니다.  
  
 `piHashAlg`  
 [out에서] 해시를 생성할 때 사용 하는 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다. 경우 `piHashAlg` CALG_SHA-1은 사용 되는 기본 알고리즘 0으로 설정 됩니다.  
  
 `pbHash`  
 [out] 생성된 된 해시를 포함 하는 바이트 배열입니다.  
  
 `cchHash`  
 [in] 버퍼의 최대 크기는 `pbHash` 를 가리킵니다.  
  
 `pchHash`  
 [out] 반환 된 바이트 단위로 크기 `pbHash`합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 동일 [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)제외 하 고 파일 이름 지정이 유니코드 대신 ANSI 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetHashFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [GetHashFromFileW 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
