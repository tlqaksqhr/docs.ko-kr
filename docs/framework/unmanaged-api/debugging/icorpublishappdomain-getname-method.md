---
title: ICorPublishAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423860"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName 메서드
이 표시 되는 응용 프로그램 도메인의 이름을 가져옵니다 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cchName`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 [out] 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터는 `szName` 배열입니다.  
  
 `szName`  
 [out] 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 경우 `szName` 은 null이 아니며는 `GetName` 메서드 최대 복사 `cchName` 까지의 문자 (null 종결자 포함) `szName`합니다. Null이 아닌 반환 되는 `pcchName`을 실제 이름 (null 종결자 포함)에 문자 수에 저장 됩니다는 `szName` 배열입니다.  
  
 `GetName` 메서드 복사 된 문자 수에 관계 없이 s_ok이 고 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorPublishAppDomain 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
