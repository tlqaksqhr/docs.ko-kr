---
title: IMetaDataEmit::DefineTypeDef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54691785e3b2619b5f4a2eecc510800b4b5cee07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446599"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef 메서드
공용 언어 런타임 형식에 대 한 형식 정의 만들고 해당 형식 정의 대 한 메타 데이터 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szTypeDef`  
 [in] 유니코드에 대 한 형식의 이름입니다.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` 특성입니다. 이 비트 마스크의 `CoreTypeAttr` 값입니다.  
  
 `tkExtends`  
 [in] 기본 클래스의 토큰입니다. 중 하나 이어야 합니다는 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.  
  
 `rtkImplements`  
 [in] 이 클래스 또는 인터페이스를 구현 하는 인터페이스를 지정 하는 토큰의 배열입니다.  
  
 `ptd`  
 [out] `mdTypeDef` 할당 된 토큰입니다.  
  
## <a name="remarks"></a>설명  
 플래그 `dwTypeDefFlags` 생성 될 형식이 공용 형식 시스템 참조 형식 (클래스 또는 인터페이스) 또는 공용 형식 시스템 값 형식 인지를 지정 합니다.  
  
 제공 된 매개 변수에 따라이 메서드를 파생 작업으로 만들 수도 있습니다는 `mdInterfaceImpl` 이 형식에 의해 구현 되거나 상속 되는 각 인터페이스에 대 한 레코드입니다. 그러나이 메서드는 반환 하지는 이러한 `mdInterfaceImpl` 토큰입니다. 클라이언트가 나중에 추가 하거나 수정 하려는 경우는 `mdInterfaceImpl` 토큰을 사용 하 여 해야는 `IMetaDataImport` 인터페이스를 열거 합니다. COM 의미 체계를 사용 하려는 경우는 `[default]` 인터페이스에서 첫 번째 요소로 기본 인터페이스를 제공 해야 `rtkImplements`; 클래스에 설정 하는 사용자 지정 특성은 기본 인터페이스에 표시 됩니다 (되도록 항상 가정 된는 먼저 `mdInterfaceImpl` 클래스에 대해 선언 된 토큰)입니다.  
  
 각 요소는 `rtkImplements` 보류 배열는 `mdTypeDef` 또는 `mdTypeRef` 토큰입니다. 배열의 마지막 요소 여야 합니다 `mdTokenNil`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
