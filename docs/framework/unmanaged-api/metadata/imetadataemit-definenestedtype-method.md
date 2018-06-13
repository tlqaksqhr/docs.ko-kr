---
title: IMetaDataEmit::DefineNestedType 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0d105679a749b8c87099af871bdb42874d440b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447005"
---
# <a name="imetadataemitdefinenestedtype-method"></a>IMetaDataEmit::DefineNestedType 메서드
형식 정의의 메타 데이터 서명을 만듭니다, 반환 된 `mdTypeDef` 정의 된 형식에서 참조 형식의 멤버 임을 지정 하 고 해당 형식에 대 한 토큰는 `tdEncloser` 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szTypeDef`  
 [in] 유니코드에 대 한 형식의 이름입니다.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` 특성입니다. 이 비트 마스크의 `CorTypeAttr` 값입니다.  
  
 `tkExtends`  
 [in] 기본 클래스의 토큰입니다. 이 역할은 한 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.  
  
 `rtkImplements`[]  
 [in] 이 클래스 또는 인터페이스를 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.  
  
 `tdEncloser`  
 [in] 바깥쪽 형식의 토큰입니다. 배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.  
  
 `ptd`  
 [out] `mdTypeDef` 할당 된 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
