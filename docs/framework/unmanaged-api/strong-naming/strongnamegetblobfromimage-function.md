---
title: StrongNameGetBlobFromImage 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d562aef58c1e3b5bbbe690b54eb08384052c657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456777"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage 함수
지정 된 메모리 주소에서 어셈블리 이미지의 이진 표현을 가져옵니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbBase`  
 [in] 매핑된 어셈블리 매니페스트에의 메모리 주소입니다.  
  
 `dwLength`  
 [in] 에 있는 이미지를 바이트 단위로 크기 `pbBase`합니다.  
  
 `pbBlob`  
 [in] 이미지의 이진 표현을 포함 하는 버퍼입니다.  
  
 `pcbBlob`  
 [out에서] 최대 크기를 바이트, 요청 된 `pbBlob`합니다. 반환 되 면 실제 크기를 바이트 단위로 `pbBlob`합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 경우는 `StrongNameGetBlobFromImage` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameGetBlobFromImage 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [StrongNameGetBlob 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
