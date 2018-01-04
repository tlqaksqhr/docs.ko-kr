---
title: "StrongNameKeyInstall 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a8dbc84f375b7bbbad47971936650d81c5c63df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall 함수
컨테이너에 공개/개인 키 쌍을 가져옵니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameKeyInstall (  
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
 `true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) 키 컨테이너를 삭제 하는 함수입니다.  
  
 경우는 `StrongNameKeyInstall` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** WindSee [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameKeyInstall 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [StrongNameKeyDelete 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
