---
title: "IMetaDataEmit::DefineTypeRefByName 메서드"
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
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName 메서드
현재 범위 밖에 있는 지정된 된 범위에 정의 된 형식에 대 한 메타 데이터를 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tkResolutionScope`  
 [in] 결정 범위를 지정 하는 토큰입니다. 다음 토큰 형식을 유효한은 같습니다.  
  
-   `mdModuleRef`는 형식이 호출자에 게 정의 되어 있는 동일한 어셈블리에 정의 되어 있습니다.  
  
-   `mdAssemblyRef`는 형식이 호출자에 게 정의 되어 있는 것과 다른 어셈블리에 정의 되어 있습니다.  
  
-   `mdTypeRef`는 형식이 중첩된 형식이 면 합니다.  
  
-   `mdModule`형식을 호출자가 정의 하는 동일한 모듈에 정의 된 경우.  
  
-   전역으로 정의 된 경우 null입니다.  
  
 `szName`  
 [in] 유니코드에서는 대상 형식의 이름입니다.  
  
 `ptr`  
 [out] 에 대 한 포인터는 `mdTypeRef` 토큰 형식에 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
