---
title: "ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b8b3437d8c07cd57a4791995890cab1b06aafc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a>ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드
지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키 토큰을 나타내는 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszFilePath`  
 [in] 경로 어셈블리에 대 한 이식 가능한 실행 (PE) 파일입니다.  
  
 `ppbStrongNameToken`  
 [out] 반환 된 강력한 이름 토큰입니다.  
  
 `pcbStrongNameToken`  
 [out] 강력한 이름 토큰의 바이트 크기입니다.  
  
 `ppbPublicKeyBlob`  
 [out] 반환 된 공개 키입니다.  
  
 `pcbPublicKeyBlob`  
 [out] 공개 키를 바이트 단위로 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="remarks"></a>설명  
 강력한 이름 토큰에는 공개 키의 축약 된 형식입니다. 토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 생성 되는 64 비트 해시입니다. 어셈블리에 대 한 강력한 이름의 일부인 토큰과 어셈블리 메타 데이터에서 읽을 수 있습니다.  
  
 호출 해야 키를 검색 한 후 토큰이 생성 됩니다는 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 할당 된 메모리를 해제 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameTokenFromAssembly 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
