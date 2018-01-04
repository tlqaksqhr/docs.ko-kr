---
title: "IMetaDataEmit::SetTypeDefProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a03b781865b55b832b34bfdab7c88ce33f4e9e12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsettypedefprops-method"></a>IMetaDataEmit::SetTypeDefProps 메서드
이전 호출에서 정의 된 형식 기능을 설정 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] `mdTypeDef` 토큰에 대 한 원래 호출에서 얻은 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` 특성입니다. 이 비트 마스크의 `CorTypeAttr` 값입니다.  
  
 `tkExtends`  
 [in] `mdToken` 기본 클래스입니다. 에 대 한 이전 호출에서 가져온 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), 또는 `null`합니다.  
  
 `rtkImplements[]`  
 [in] 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다. 이러한 `mdTypeRef` 토큰을 사용 하 여 가져오는 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)합니다. 배열의 마지막 요소는 해야 `mdTokenNil`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
