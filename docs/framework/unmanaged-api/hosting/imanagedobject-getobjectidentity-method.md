---
title: IManagedObject::GetObjectIdentity 메서드
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1975e5bf20453a3bcd6761d9734be7ddd2ceef7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440329"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity 메서드
이 관리 되는 개체의 id를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBSTRGUID`  
 [out] 개체가 상주 하는 프로세스의 GUID에 대 한 포인터입니다.  
  
 `AppDomainID`  
 [out] 개체의 응용 프로그램 도메인의 ID에 대 한 포인터입니다.  
  
 `pCCW`  
 [out] COM 클래식 v 테이블에서 개체의 인덱스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 관리 되는 개체의 id COM 클래식 v 테이블에서는 GUID 프로세스, 응용 프로그램 도메인 ID 및 개체의 인덱스를 포함합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IManagedObject 인터페이스](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
