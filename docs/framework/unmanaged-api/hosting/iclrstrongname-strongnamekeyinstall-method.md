---
title: "ICLRStrongName::StrongNameKeyInstall 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df1bdb5d6d6018855cb76b48d58e557a61288a51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a>ICLRStrongName::StrongNameKeyInstall 메서드
컨테이너에 공개/개인 키 쌍을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszKeyContainer`  
 [in] 키 컨테이너의 이름입니다. `wszKeyContainer`비어 있지 않은 문자열 이어야 합니다.  
  
 `pbKeyBlob`  
 [in] 이진 키 쌍입니다.  
  
 `cbKeyBlob`  
 [in] 를 바이트 단위로 크기의 `pbKeyBlob`합니다.  
  
## <a name="return-value"></a>반환 값  
 `S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="remarks"></a>설명  
 사용 하 여는 [iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드 키 컨테이너를 삭제 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameKeyDelete 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
