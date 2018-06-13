---
title: ICLRStrongName::StrongNameCompareAssemblies 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5020c31f590f527856f966ede512e98c07496ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435390"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies 메서드
두 어셈블리가 강력한 이름 서명만 다른 지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StrongNameCompareAssemblies (  
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
 `S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>설명  
 어셈블리의 강력한 이름 서명을 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 이루어져 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
