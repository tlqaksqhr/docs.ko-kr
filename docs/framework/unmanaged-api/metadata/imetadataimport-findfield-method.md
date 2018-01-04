---
title: "IMetaDataImport::FindField 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3178d3ff3c64de5390e1150445f0c49c560aa32a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField 메서드
한 포인터를 가져옵니다 FieldDef 토큰 묶여 있는 필드에 대 한 지정 된 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] 해당 클래스 또는 인터페이스를 검색할 필드를 포함 하는 TypeDef 토큰입니다. 이 값이 `mdTokenNil`, 전역 변수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 [in] 검색할 필드의 이름입니다.  
  
 `pvSigBlob`  
 [in] 필드의 이진 메타 데이터 서명에 대 한 포인터입니다.  
  
 `cbSigBlob`  
 [in] 바이트 크기 `pvSigBlob`합니다.  
  
 `pmb`  
 [out] 일치 하는 FieldDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스를 사용 하 여 필드를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`).  
  
 에 전달 된 서명을 `FindField` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다. 서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다. (토큰은 로컬 TypeDef 테이블에 대 한 인덱스). 현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 대 한 입력으로 사용할 수는 없습니다 `FindField`합니다.  
  
 `FindField`클래스 또는 인터페이스에 직접 정의 된 필드를만 찾습니다. 상속 된 필드는 찾지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
