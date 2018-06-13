---
title: IMetaDataEmit::DefineImportMember 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9995fda70d1d5a3c19c30496de6c32f20015d47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449392"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember 메서드
형식이 나 현재 범위를 벗어난 정의 되 고 해당 참조에 대 한 토큰을 정의 하는 모듈의 지정된 된 멤버에 대 한 참조를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAssemImport`  
 [in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 대상 멤버를 가져올 어셈블리를 나타내는 인터페이스입니다.  
  
 `pbHashValue`  
 [in] 로 지정 된 어셈블리에 대 한 해시를 포함 하는 배열 `pAssemImport`합니다.  
  
 `cbHashValue`  
 [in] `pbHashValue` 배열의 바이트 수입니다.  
  
 `pImport`  
 [in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 대상 멤버를 가져올 메타 데이터 범위를 나타내는 인터페이스입니다.  
  
 `mbMember`  
 [in] 대상 멤버를 지정 하는 메타 데이터 토큰입니다. 토큰 일 수 있습니다는 `mdMethodDef` (멤버 방법의 경우)에 대 한 `mdProperty` (에 대해 멤버 속성의 경우) 또는 `mdFieldDef` (멤버 필드)에 대 한 토큰입니다.  
  
 `pAssemEmit`  
 [in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) 대상 멤버를 가져올 어셈블리를 나타내는 인터페이스입니다.  
  
 `tkParent`  
 [in] `mdTypeRef` 또는 `mdModuleRef` 형식이 나 모듈에 대 한 토큰을 각각 소유 하는 대상 멤버입니다.  
  
 `pmr`  
 [out] `mdMemberRef` 멤버 참조에 대 한 현재 범위에 정의 된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 `DefineImportMember` 메서드로 지정 된 멤버를 찾습니다 `mbMember`, 즉로 지정 된 다른 범위에 정의 된 `pImport`, 해당 속성을 검색 하 고 있습니다. 이 정보를 사용 하 여 호출 하 여 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 멤버 참조를 만들 수는 현재 범위에서 메서드.  
  
 일반적으로 사용 하기 전에 `DefineImportMember` 메서드를 만들어야 합니다, 현재 범위, 형식 참조 또는 대상 멤버의 부모 클래스, 인터페이스 또는 모듈에 대 한 모듈 참조. 이 참조에 대 한 메타 데이터 토큰에 전달 됩니다는 `tkParent` 인수입니다. 컴파일러 또는 링커가 나중에 해결할 수는 대상 멤버의 부모에 대 한 참조를 만들 필요가 없습니다. 요약:  
  
-   대상 멤버 필드 또는 메서드를 사용 중인 경우 하나는 [imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 또는 [imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) 방법을 사용에 대 한 현재 범위에 형식 참조를 만들 수는 멤버의 부모 클래스 또는 부모 인터페이스입니다.  
  
-   사용 하 여 대상 멤버가 전역 변수 또는 전역 함수 (즉, 하지 멤버 클래스 또는 인터페이스의) 인 경우는 [imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) 멤버의 부모에 대 한 현재 범위에서 모듈 참조를 만드는 메서드를 모듈입니다.  
  
-   대상 멤버의 부모에 의해 컴파일러 또는 링커 나중에 확인 될를 전달 합니다 `mdTokenNil` 에서 `tkParent`합니다. 이 적용 되는 유일한 시나리오는 경우 전역 함수 또는 전역 변수를 현재 모듈에 연결 될.obj 파일에서 가져오는 및 메타 데이터를 병합 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
