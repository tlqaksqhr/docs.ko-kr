---
title: "IMetaDataAssemblyEmit::DefineExportedType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineExportedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59aae188e404ebc717a140fb7918e3fbf69f3f70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType 메서드
지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szName`  
 [in] 내보낼 수 있는 형식의 이름입니다. 공용 언어 런타임 내보낸 형식의 이름은의 버전 1.1에 지정 된 이름과 정확히 일치 해야에 대 한는 `TypeDef` 유형에 대 한 합니다.  
  
 `tkImplementation`  
 [in] 내보낸된 형식을 구현 하는 지정 하는 토큰입니다. 유효한 값 및 관련된 의미는 합니다.  
  
-   `mdFile`형식이이 어셈블리 내의 다른 파일에 구현 됩니다.  
  
-   `mdAssemblyRef`형식이 다른 어셈블리에 구현 됩니다.  
  
-   `mdExportedTYpe`형식이 다른 형식에 중첩 합니다.  
  
-   `mdFileNil`매니페스트와 같은 파일에 형식과 중첩 된 형식이 아닙니다.  
  
 `tkTypeDef`  
 [in] 내보낼 형식을 지정 하는 메타 데이터 토큰입니다. 이 값은 입력의 `TypeDef` 형식을 구현 하 고이 파일은이 어셈블리의 경우에 해당 하는 파일에는 테이블입니다.  
  
 `dwExportedTypeFlags`  
 [in] 비트 조합 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 내보낸된 형식에 대 한 속성 설정을 정의 하는 열거형 값입니다.  
  
 `pmdct`  
 [out] 내보낸된 형식을 나타내는 반환 된 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `ExportedType` 이 어셈블리에 의해 노출 되는 매니페스트를 포함 하는 것과 다른 모듈에 구현 되는 각 형식에 대 한 메타 데이터 구조를 정의 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
