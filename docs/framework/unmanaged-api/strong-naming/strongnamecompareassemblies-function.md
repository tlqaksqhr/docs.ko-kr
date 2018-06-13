---
title: StrongNameCompareAssemblies 함수
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd1d098f21a3d5ba43b6251c87c36df4347a924
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457563"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies 함수
두 어셈블리가 강력한 이름 서명만 다른 지 여부를 결정 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 하 여 [iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszAssembly1`  
 [in] 첫 번째 어셈블리에 대 한 경로입니다.  
  
 `wszAssembly2`  
 [in] 두 번째 어셈블리에 대 한 경로입니다.  
  
 `pdwResult`  
 [out] 다음 값 중 하나입니다.  
  
-   `SN_CMP_DIFFERENT` (0)-어셈블리가 서로 다른 데이터를 포함 하도록 지정 합니다.  
  
-   `SN_CMP_IDENTICAL` (1)-어셈블리를 정확히 동일한 경우 해당 서명과 체크섬을 포함 하 여 지정 합니다.  
  
-   `SN_CMP_SIGONLY` (2)-서명 및 체크섬을 통해서만 어셈블리가 서명만 다른 지를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>설명  
 어셈블리의 강력한 이름 서명을 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 이루어져 있습니다.  
  
 경우는 `StrongNameCompareAssemblies` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [StrongNameCompareAssemblies 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
