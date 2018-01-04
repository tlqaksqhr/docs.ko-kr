---
title: "IMetaDataEmit::DefineImportType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fee13c88cc39398808ad1ff481e602d63e8f39f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimporttype-method"></a>IMetaDataEmit::DefineImportType 메서드
현재 범위를 벗어난 정의 되 고 해당 참조에 대 한 토큰을 정의 하는 지정된 된 형식에 대 한 참조를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAssemImport`  
 [in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 대상 유형을 가져올 어셈블리를 나타내는 인터페이스입니다.  
  
 `pbHashValue`  
 [in] 로 지정 된 어셈블리에 대 한 해시를 포함 하는 배열 `pAssemImport`합니다.  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 [in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 대상 유형을 가져올 메타 데이터 범위를 나타내는 인터페이스입니다.  
  
 `tdImport`  
 [in] `mdTypeDef` 대상 형식을 지정 하는 토큰입니다.  
  
 `pAssemEmit`  
 [in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 대상 형식을 가져오는 어셈블리를 나타내는 인터페이스입니다.  
  
 `ptr`  
 [out] `mdTypeRef` 형식 참조에 대 한 현재 범위에 정의 된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 호출 하기 전에 [imetadataemit:: Defineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) 사용할 수는 `DefineImportType` 멤버의 부모 클래스 또는 부모 인터페이스에 대 한 현재 범위에 대 한 형식 참조를 만드는 메서드를 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
