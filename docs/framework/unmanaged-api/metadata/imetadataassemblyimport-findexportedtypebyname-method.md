---
title: "IMetaDataAssemblyImport::FindExportedTypeByName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindExportedTypeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7ef0e09cb5a44e612e545fc4ee7278c2d128174
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>IMetaDataAssemblyImport::FindExportedTypeByName 메서드
해당 이름 및 바깥쪽 형식 지정 된 내보낸된 형식에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szName`  
 [in] 내보낸 형식의 이름입니다.  
  
 `mdtExportedType`  
 [in] 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다. 이 값은 `mdExportedTypeNil` 요청 된 내보낸가 아니면 중첩된 형식입니다.  
  
 `ptkExportedType`  
 [out] 에 대 한 포인터는 `mdExportedType` 내보낸된 형식 나타내는 토큰입니다.  
  
## <a name="remarks"></a>설명  
 `FindExportedTypeByName` 메서드는 참조를 확인 하기 위한 공용 언어 런타임에서 표준 규칙을 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [런타임에서 어셈블리를 찾는 방법](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
