---
title: IsFrameworkAssembly 함수
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429252"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly 함수
지정된 된 어셈블리 관리 되는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzAssemblyReference`  
 [in] 확인할 어셈블리의 이름입니다.  
  
 `pbIsFrameworkAssembly`  
 [out] 어셈블리 관리 되는지 여부를 나타내는 부울 값입니다.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] 어셈블리의 고유 id를 포함 하는 uncanonicalized 문자열입니다.  
  
 `pccSize`  
 [in] `pwzFrameworkAssemblyIdentity`의 크기입니다.  
  
## <a name="remarks"></a>설명  
 `pwzAssemblyReference` 매개 변수는 어셈블리의 이름이 포함 된 문자열에 대 한 포인터입니다.  
  
 이 어셈블리는.NET Framework의 일부인 경우는 `pbIsFrameworkAssembly` 매개 변수는 부울 값을 포함 됩니다 `true`합니다.  
  
 명명된 된 어셈블리는.NET Framework의 일부가 아닌 경우 또는 경우는 `pwzAssemblyReference` 매개 변수는 어셈블리 이름을 지정 하지 않습니다 `pbIsFrameworkAssembly` 의 부울 값이 포함 됩니다 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
