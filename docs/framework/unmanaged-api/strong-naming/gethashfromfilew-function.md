---
title: "GetHashFromFileW 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFileW
helpviewer_keywords: GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c19047f03279b1284ea8b5b8f99785cfaff5146
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW 함수
유니코드 문자열에 의해 지정 된 파일의 내용에 대 한 해시를 생성 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 해시 파일의 유니코드 이름입니다.  
  
 `piHashAlg`  
 [out에서] 해시를 생성할 때 사용 하는 알고리즘입니다. 유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다. 경우 `piHashAlg` CALG_SHA-1은 사용 되는 기본 알고리즘 0으로 설정 됩니다.  
  
 `pbHash`  
 [out] 생성된 된 해시를 포함 하는 바이트 배열입니다.  
  
 `cchHash`  
 [in] 가 가리키는 버퍼의 최대 크기 `pbHash`합니다.  
  
 `pchHash`  
 [out] 를 바이트 단위로 크기의 `pbHash`합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 동일 [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)제외 하 고 파일 이름 지정이 ANSI 대신 유니코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetHashFromFileW 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [GetHashFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
