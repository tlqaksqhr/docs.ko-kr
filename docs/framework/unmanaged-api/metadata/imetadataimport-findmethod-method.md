---
title: "IMetaDataImport::FindMethod 메서드"
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
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59cc440ba004545c31d6b25d36cca4fdfb58899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod 메서드
토큰을 가져옵니다 한 methoddef 묶여 있는 메서드에 대 한 지정 된 <xref:System.Type> 올려진 지정 된 이름 및 메타 데이터 서명을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `td`  
 [in] `mdTypeDef` 검색할 멤버를 포함 하는 형식 (클래스 또는 인터페이스)에 대 한 토큰입니다. 이 값이 `mdTokenNil`, 다음 전역 함수에 대 한 조회가 수행 됩니다.  
  
 `szName`  
 [in] 검색할 메서드 이름입니다.  
  
 `pvSigBlob`  
 [in] 이진 메타 데이터 서명 메서드의 포인터입니다.  
  
 `cbSigBlob`  
 [in] 바이트 크기 `pvSigBlob`합니다.  
  
 `pmb`  
 [out] 일치 하는 MethodDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 바깥쪽 클래스 또는 인터페이스를 사용 하 여 메서드를 지정 (`td`), 해당 이름 (`szName`), 및 선택적 요소인 시그니처 (`pvSigBlob`). 클래스 또는 인터페이스에 동일한 이름 가진 메서드가 여러 개 있을 수 있습니다. 이 경우 전달 메서드 시그니처 고유 일치 항목을 찾습니다.  
  
 에 전달 된 서명을 `FindMethod` 서명에 특정 범위에 바인딩되어 있기 때문에 현재 범위에서 생성 해야 합니다. 서명을 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰을 포함할 수 있습니다. 토큰은 로컬 TypeDef 테이블에 대 한 인덱스. 현재 범위의 컨텍스트 외부에서 런타임에 서명을 한에 입력으로 사용할 수는 없습니다 `FindMethod`합니다.  
  
 `FindMethod`클래스 또는 인터페이스에 직접 정의 된 메서드만을 찾습니다. 상속 된 메서드를 찾지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.MethodInfo>  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
