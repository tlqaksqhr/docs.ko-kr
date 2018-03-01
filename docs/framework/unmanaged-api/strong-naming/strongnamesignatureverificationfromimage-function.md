---
title: "StrongNameSignatureVerificationFromImage 함수"
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
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 178dcbae4f8ec40ac9ef14fc00109c83ab87c21a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage 함수
연결된 된 공개 키가 이미 메모리에 매핑되어 있는 어셈블리가 올바른지 확인 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbBase`  
 [in] 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.  
  
 `dwLength`  
 [in] 매핑된 이미지를 바이트 단위로 크기입니다.  
  
 `dwInFlags`  
 [in] 확인 동작에 영향을 주는 플래그입니다. 다음 값이 지원 됩니다.  
  
-   `SN_INFLAG_FORCE_VER`(0x00000001)-강제로 레지스트리 설정을 재정의 해야 하는 경우에 확인 합니다.  
  
-   `SN_INFLAG_INSTALL`(0x00000002)-이 이미지에 수행 된 첫 번째 확인 임을 지정 합니다.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0x00000004)-캐시 관리 권한이 있는 사용자 에게만 액세스를 사용할 수 있음을 지정 합니다.  
  
-   `SN_INFLAG_USER_ACCESS`(0x00000008)-어셈블리 현재 사용자에만 액세스할 수 있는지를 지정 합니다.  
  
-   `SN_INFLAG_ALL_ACCESS`(0x00000010)-캐시의 액세스 제한이 않음을 지정 합니다.  
  
-   `SN_INFLAG_RUNTIME`(0x80000000)-내부 디버깅 하기 위해 예약 되어 있습니다.  
  
 `pdwOutFlags`  
 [out] 출력 추가 정보에 대 한 플래그입니다. 다음 값이 지원 됩니다.  
  
-   `SN_OUTFLAG_WAS_VERIFIED`이 값은로 설정 (0x00000001)- `false` 확인 레지스트리 설정으로 인해 성공 했는지를 지정 하려면.  
  
## <a name="return-value"></a>반환 값  
 `true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 경우는 `StrongNameSignatureVerificationFromImage` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** mscoree.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameSignatureVerificationFromImage 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
