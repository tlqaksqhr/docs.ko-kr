---
title: "IMetaDataImport::GetNameFromToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNameFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e77954d5730417a005c6c1ac07fa171bd0f1b13a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a>IMetaDataImport::GetNameFromToken 메서드
지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다. 이 메서드는 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `tk`  
 [in] 에 대 한 이름을 반환 하 고 개체를 나타내는 토큰입니다.  
  
 `pszUtf8NamePtr`  
 [out] 힙에 있는 u t F-8 개체 이름에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetNameFromToken`는 사용되지 않습니다. 대신 특정 유형의 같은 필요한 토큰의 속성을 가져오는 메서드를 호출 `GetFieldProps` 필드 또는 `GetMethodProps` 메서드에 대 한 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** 1.0  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
